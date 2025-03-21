---
{"dg-publish":true,"permalink":"/Process Synchronisation/","tags":["CompSci"]}
---

***Created on: 10/10/2023
Last updated: 13/10/2023***

----
# Index/Contents
[[Process Synchronisation#1. What is Race Condition?\|#1. What is Race Condition?]]
[[Process Synchronisation#2. What are the types of Processes in terms of dependence?\|#2. What are the types of Processes in terms of dependence?]]
[[Process Synchronisation#3. Producer-Consumer Problem\|#3. Producer-Consumer Problem]]
[[Process Synchronisation#4. Printer-Spooler Problem\|#4. Printer-Spooler Problem]]
[[Process Synchronisation#5. Critical-Section Problem\|#5. Critical-Section Problem]]
[[Process Synchronisation#6. Synchronisation Mechanism & Conditions\|#6. Synchronisation Mechanism & Conditions]]
[[Process Synchronisation#Reference Material and Footnotes\|#Reference Material and Footnotes]]

-----
# 1. What is Race Condition?
A situation where ***several processes access and manipulate the ==same data concurrently==*** and the outcome of the execution ***depends on the ==particular order== in which the access takes place***, is called a ==***Race Condition***==.
Race Condition always creates wrong data or even create a problem of data loss. Hence it is not desirable
To prevent such a condition and guard against it, we need that the processes be synchronised in some way. $\large^{[1]}$

----
# 2.  What are the types of Processes in terms of dependence?
There are two types of Processes that we study in this chapter:
1. ***Cooperative Processes***: A change in one process may create a change in another. Generally this "cooperation" is caused by some shared aspects like Variables, Memory, Code and/or Hardware (called "Resources" hereafter) etc.
2. ***Independent Processes***: Change in one process does not affect any other process. There is nothing special about learning about these processes.

We won't talk about any situation where Cooperative Processes are running serially - since then there is no problem.
This Synchronisation concept is very similar to Transactions from a similar subject (Database Systems and Web - also called DBMS) in the 3rd semester.

---
# 3. Producer-Consumer Problem
There are two processes - one that produces data and the other that consumes data. Check [[Process Concept#Shared-Memory Systems\|Process Concept#Shared-Memory Systems]] and the [[Process Synchronisation#^2\|#^2]] for more info.

---
# 4. Printer-Spooler Problem
***Assumption***: One Printer for a network of users. Since Printers are slower than CPUs, there is a computer program known as "Spooler" which iteratively sends Print Commands from the computer to the Printer on a FCFS basis.
***Problem***: Sometimes, if the processes are un-synchronised and there are 2 processes wanting to add their document to the printing queue, then they can add it on the same location block overriding one of the two. ***Loss of data is a very big problem***.
[Gate Smashers Video (L-3.3) on this topic](https://www.youtube.com/watch?v=16NMm0jvu2w&list=PLxCzCOWd7aiGz9donHRrE9I3Mwn6XdP8p&index=27)

---
# 5. Critical-Section Problem
Part of the program where shared resources are accessed by various cooperative processes.
Critical Section must not be accessed by more than one program to avoid Race Condition (Please see [[Process Synchronisation#1. What is Race Condition?\|#1. What is Race Condition?]] for more info)

---
# 6. Synchronisation Mechanism & Conditions
To synchronise a pair (or group) of processes, we need to add a few lines of code before their Critical Section Code (CSC). These lines are known as "Entry Section Code" (ESC). They are written as a mechanism to synchronise the processes using The 4 Synchronisation Conditions.
These are 4 conditions that must be satisfied to say that a particular solution is viable.
1. ==***Mutual Exclusion***==: If a process P1 is already in the Critical Section, then another process (Let's say, P2) cannot enter the critical section until P1 exits.
2. ==***Progress***==: Any process that wants to enter the CSC must not be stopped as long as there are no other processes inside the CSC.$\large^{[3]}$
3. ==***Bounded Wait***==: Some processes may use the CSC disproportionately but none should be starved. None of the processes should keep on using the CSC for $\Large\infty$ amount of time.  
4. ==***No Assumption related to Hardware Speed***==: Should work on all hardware and across OS and be portable. Should not put a minimum speed limit (Example: Your Solution should not fail for CPU speeds under 1GHz)

The first two conditions are Primary conditions. Hence following them is a must.
The following two conditions are Secondary, may not be the most important and may be skipped but it is still preferred if the particular proposed solution takes them in account too.

---
# 7. Solution 1: LOCK variable
Oldest way of dealing with Synchronisation issues.
`LOCK` is a binary variable, it is either 0 (CSC vacant) or 1 (CSC full)
it is implemented using the folowing code:
```Cpp
// Entry Code
while(LOCK==1); // Alternate Statement: while(LOCK!=0)
LOCK=1;
```
Note that any preemption between Line 1 and Line 2 can cause misunderstanding, another process P2 can execute both lines and get into the CSC, when the context switches back to the original process (say, P1) and P1 starts executing from where it left off at Line 2, it won't care if the value of LOCK was 1 beforehand or not. 
It will just go inside CSC after editing the LOCK value. 
***RIP Mutual Exclusion***.
```Cpp
// Exit Code
LOCK=0;
```

## 7.1 Better Solution - using T&S
Here T&S refers to Test and Set - a singular variable that both tests if the value of LOCK is 1 ***AND*** sets the value of LOCK to 1 i.e., T&S combines Line 1 and Line 2 of the initial entry code.
```Cpp
while(test_and_set(&lock))
// Critical Section code here
lock = False;
bool test_and_set(boolean*target)
{
	bool r = *target;
	*target = True;
	return r;
}
```
the `&lock` uses call by reference (using pointer)
target is a pointer which is pointing to the value of `&lock`
Value of `lock` is placed in r.
`target` is now made true.
As long as CSC is empty, any process is allowed to enter. Hence Progress is also acheived.

---
# 8. Solution 2: Turn Variable (Strict)
This Solution is only applicable for 2 processes.
Turn variable is binary (like LOCK)
It can take value 0 or 1 at initialisation to initialise $\large P_0$ or $\large P_1$ respectively.
```C
// Process P0
while(turn!=0);
turn = 0;
```

```C
// Process P1
while(turn!=1)
turn = 1;
```
It is mutually exclusive but if turn = 0, then only $\large P_1$ can enter. 
Hence, 
Mutual Exclusion $\checkmark$ 
Progress $\chi$ 

To achieve we use Flag Array in conjunction with the turn variable.
The Flag Array is an array of boolean values that are used to check if a certain process wants to get inside the critical section or not. Whichever does, will turn their Flag to 1 (i.e., True).
```C
// Process P0
flag[0]=1;
turn = 1;
while(turn==1&&flag[1]==1);
// allowed inside critical section if while loop is false.
flag[0]=0;
//P0 exits critical section
```

```C
// Process P1
flag[1]=1;
turn = 1;
while(turn==0&&flag[0]==1);
// allowed inside critical section if while loop is false.
flag[1]=0;
//P1 exits critical section
```

---
# 9. Semaphores
A Semaphore is an integer variable used in a Mutually Exclusive manner by various Concurrent (Parallel) Cooperative Process in order to acheive synchronisation.
Used in 2 types:
1. Counting (values from $\large- \infty$ to $\large+ \infty$)
2. Binary (value either 0 or 1)

Operations in Semaphores
1. Down (also called Wait or P)
2. Up (also called Signal or V)

CSC Entry ke liye Down ka code run karna padega
CSC Exit ke liye Up ka code run karna padega

## 9.1 The Counting Semaphore Code (Both Cycles: Up and Down)
Code taken from Gate Smashers Video L-3.8 in Operating Systems Playlist.

```Cpp
//Entry Section Code for Semaphore S
Down(S){
	S = S - 1;
	if(S<0){
		//Put process (PCB) in suspend list
		Sleep();
	}
	else{
		return;
	}
}
// Down is also called P(), Wait()
// For Mutual Exclusion, S == 1
```

```Cpp
// Exit Section Code for Sempahore S
UP(S){
	S = S + 1;
	if(S<=0){
		// Select a process from suspend list
		Wake();
	}
	else{
		return;
	}
}
// UP is also called V, Signal(), Post() etc.
// For Mutual Exclusion, S == 1.
```
A code awoken by `Wake();` command in UP means that the specific process can try agaiin, it is not spawned inside Critical Section (CSC).
As long as `S == 0;` is true, then there are 0 processes in suspend list. Also, S = Number of maximum processes that can enter the CSC.
## 9.2 The Binary Semaphore Code (Both Cycles: Up and Down)
Code taken from Gate Smashers Video L-3.9 from their Operating Systems Playlist.
```Cpp
// Down Cycle
DOWN(S){
	if(S==1) {
		S=0;
	}
	else {
		//Block this process and place in Suspend List
		Sleep();
	}
}
```

```Cpp
// Up Cycle
UP(S){
	if(Suspend_list = is_empty()){ //
		S=1;
	}
	else {
		// Select a process from Suspend List
		Wake();
	}
}
```

## 9.3 Semphore Code from Refernce Book
Taken from Chapter 6, Section 6.5, Page 234 in the book. Reference Book Details are: [[Process Synchronisation#^1\|#^1]].
```C
//For Wait (i.e., DOWN) Operation 
wait(S){
	while(S<=0){
		;// no-operation
	}
	S--;
}

//For Signal (i.e., UP) Operation
signal(S){
	S++;
}
```

The next sub-section in the book - named "Usage" describes how these are used.
> *The value of a **counting semaphore** can range over an unrestricted domain. The value of a **binary semaphore** can range only between 0 and 1. On some systems binary semaphores are known as **mutex locks**. Since they provide **mut**ual **ex**clusion.* (Page 234-235)

It also further states:
> *Each Process that wishes to use a resource performs a `wait();` operation on the semaphore (decrementing the count). When a process releases a resource, it performs a `signal();` operation (incrementing the count)* (Page 235)

***==Main Disadvantage of using Sephamores:==***
> *"The main disadvantage of the semaphore definition given here is that it requires **busy waiting**. While the process is in its critical section, any otheer process trying to enter its critical section must loop continuously in the entry code. This continual looping is clearly a problem in a real multiprogramming system, where a single CPU is shared among many processes. Busy waiting wastes CPU cycles that some other processs might be able to use productively. This type of semaphore is also called a **spinlock** since the locked processes have to spin waiting for the lock". ==Spinlocks are extensively seen when Context Switching time needs to be saved and locks are expected to be held for short times. Like a multiprocessor system==* (Page 235-236)

---
Next Chapter ---> [[File System Structure\|File System Structure]]
# Reference Material and Footnotes
$\large^{[1]}$ Operating Systems Concepts - Abraham Silberschatz et. al. (J128 LRC section 5.43)
{ #1}


$\large^{[2]}$ [Operating Systems YouTube Playlist](https://www.youtube.com/playlist?list=PLxCzCOWd7aiGz9donHRrE9I3Mwn6XdP8p) - Gate Smashers (L-3.1 to L-3.13)
{ #2}


$\large^{[3]}$ Lack of Progress can be understood by the following example: There are no processes in the CSC but P1 is blocked by P2 due to some lines of code in the ESC - classic example of "I am not gonna let you progress, neither will I."
{ #3}
