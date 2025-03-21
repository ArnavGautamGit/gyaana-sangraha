---
{"dg-publish":true,"permalink":"/Process Scheduling/","tags":["CompSci"]}
---


----
# Index/Contents
[[Process Scheduling#1. What is Process Scheduling?\|#1. What is Process Scheduling?]]
[[Process Scheduling#2. Does Process Scheduling have a criteria?\|#2. Does Process Scheduling have a criteria?]]
[[Process Scheduling#3. What are some of the famous Scheduling Algorithms?\|#3. What are some of the famous Scheduling Algorithms?]]
[[Process Scheduling#Reference Material\|#Reference Material]]

-----
# 1. What is Process Scheduling?
The *Process Scheduler* selects an available process (possibly from multiple processes) for program execution in the CPU. For single-processor systems, there are never more than 1 processes being run at a time.
## 1.1 Scheduling Queues
As processes enter the system, they are placed in a *job queue*.
The processes ready for execution but waiting are kept in the *ready queue*.
*Note: Job Queue contains all processes in the system and Ready Queues may be implemented as a linked-list.*

If there is an interruption, or if the process is waiting for some input to be given by the user, the process is moved back to the ready queue.
Even if the process creates a sub-process and that process is waiting for some user action or waiting for space to be freed up in CPU, the main process (of which the sub-process is a part) shall be moved back into the ready queue.
## 1.2 Schedulers
Even though a more common occurance in a batch system, a lot of the times, more processes are submitted that the ones that can be executed immediately.
These processes are spooled in a mass-storage device known as ==***the LTS or long-term scheduler*** (also known as ***Job Scheduler***)== 
==***The STS i.e., short-term scheduler*** (also called a ***CPU scheduler***)== selects from the processes ready to execute (after they get moved to the STS from the LTS) and allocates the CPU to one of them.
Certain system types like the Time-Sharing Systems may introduce ==***The medium-term scheduler*** (also called as the ***MTS***)== - used for reducing the degree of multiprogramming by temporarily removing the process from memory (it can be reintroduced and resumed - aka swapping)

The Schedulers need to take care of different types of processes,
*==I/O bound processes==* spend more time in I/O and hence hang around in the LTS more often.
*==CPU bound processes==* spend more time doing computations than I/O and hence hang around more often in STS.
If all I/O bound processes are selected then ready-queue is almost always empty, whereas if all CPU bound processes are selected then I/O waiting queue will be completely empty.
*==For best performance, a mix of both is required==*

## 1.3 Context Switching
Switching the CPU to another process requires performing a stable save of this current process and a state restore of a different process. This task is known as ***Context Switching.***
When a Context Switch occurs, the kernel saves the context of the old process in its PCB and loads the saved context of the new process scheduled to run.

*Example: Music Player saving which song and how much of it has been played already to resume the song from the exact same line and word where the user left off.*

Context Switching time (Time taken to switch the context) is highly dependent on hardware. Example: Some processors provide multiple sets of data to registers.
Generally, a context switch requires only changing the pointer to the current register set. However, the more complex the OS the more work has to be done during a context switch.
*Example: If there are multiple active processes, the system resorts to copying the data to-and-from memory.*
## 1.4 Preemptive Scheduling
CPU-scheduling decisions may take place under one of the following circumstances:
1. Process switches from running state to waiting state.
2. Process switches from running state to ready state.
3. Process switches from the waiting state to the ready state.
4. Process termination.
For situations 1 and 4, no choice exists between preemptive and non-preemtive scheduling, next process in ready queue gets the CPU now.
In cases 2 and 3, preemptive is used ever since Windows 95 and Mac OS X.

Non-preemptive scheduling (also called *cooperative* scheduling) is the only method that can be used on certain hardware platforms, because it does not require the special hardware needed for preemptive scheduling.

---
# 2. Does Process Scheduling have a criteria?
Yes. Many criteria have been suggested for comparing CPU scheduling algorithms.
The Process Scheduling Criteria are as follows:
- ==***CPU utilization***==: Ratio of time spent on processing information to total time CPU was on. Conceptually supposed to be between 0-100%(for light to heavy loads respectively) but it is mostly between 40-90% in real-world scenarios.
- ***==[[Throughput#Throughput in Process Scheduling\|Throughput]]==***: the number of processes completed per unit time is *Throughput*. It is a measure of work performed by the CPU.
- ==***Waiting Time (WT)***==: The WT is the sum of the period spent waiting in the ready queue. 
- ==***Turnaround Time (TAT)***==: The TAT is the sum of the periods spent waiting to get into memory, waiting in the ready queue (WT), executing in the CPU and doing I/O.
- ==***Response Time (RT)***==: The RT is the time it takes to start responding, not the time it takes to output the response. The TAT is generally limited by the speed of the output device.
***It is desirable to maximize CPU utilization and throughtput and minimize everything else (i.e., WT, RT and TAT).***
For certain time-sharing systems, it is said that reducing the variance in RT is better than trying to reduce Average-RT. A system with reasonable and *predictable* resonse time is considered much more desirable than a system which is fast on average but highly variable i.e., koi bharosa nahi hai ki fast hee chalega hamesha... isse badhiya ek consistent process ho jo consistent-sa RT leta ho.
## 2.1 Formulae Involved in numericals
$TAT = CT^{[1]} - AT^{[2]}$
$WT=TAT-BT^{[3]}$
$RT = CPU-AT$

where,
$^{[1]}CT=$ *Completion Time* - Point of time when the process finishes execution.
$^{[2]}AT =$ *Arrival Time* - Point of Time when process arrived at the Ready Queue.
$^{[3]}BT=$ *Burst Time* - Time Duration taken by the process to get executed.

Note: In cases where Non-Preemptive Scheduling is being performed, RT = WT.

---
# 3. What are some of the famous Scheduling Algorithms?
## 3.1 *First-Come, First-Served Scheduling (FCFS)*
- Simplest Scheduling Algorithm.
- Easily managed with a FIFO (First-in, First-out) queue.
- When a process enters the ready queue, its PCB (Process Control Block) is linked to the tail of the queue.

| Pros | Cons |
|------|------|
| Simple Algorithm | High Waiting Time |
| Used to resolve conflicts in other algorithms as a tiebreaker | Prone to Convoy effect where one big process can put all the small processes behind it to a halt |
| Great for similar-sized processes i.e., Processes with nearly-homogenous sizes. | Average Waiting Time depends heavily on the variance of CPU burst time, if they are very different then FCFS is slow |

## 3.2 *Shortest-Job-First Scheduling (SJF)*
- When the CPU is free, it is assigned to the the process of smallest CPU burst.
- If CPU burst is ame for two processes then FCFS is used as a tiebreaker.
- Preemptive SJF algorithm preempts the currently executing process but the non-preemptive one allows the process to finish CPU burst.
- Preemptive SJF is sometimes called *'Shortest-Remaining-Time-First-Scheduling'*.

| Pros | Cons |
|----|----|
| Optimal in most of the situations. | Can only be implemented in long-term scheduling |
| Shortest *Average* Waiting Time of all the Scheduling Algorithms | Large and Priority processes will get stuck behind smaller useless ones.|

## 3.3 *Priority Scheduling*
- A priority is associated with each process
- Priority is sometimes user defined (using specific commands) or it is defined by the shortest CPU burst gets highest priority (like SJF).
- For equal priority, FCFS is used as tiebreaker.
- When a process arrives at the ready queue, it is queued according to its priority.
- In a preemptive variant, it wil preempt the CPU if priority of the next process is more than the currently executing one. In a non-preemptive variant, it will allow the process to finish and put the new algorithm in head of the queue.

| Pros | Cons |
|----|----|
| Prioritising processes independently from size leads to short waiting times for IMPORTANT processes | Problem of *Indefinite-Blocking* (aka *Starvation*) can leave some low-priority processes to wait indefinitely |
### 3.3.1 *Starvation Problem in Priority Scheduling*
- The Starvation problem results in low-priority processes to wait indefinitely in the ready queue.
- An easy solution is the concept of ***Age***
- ***Aging*** is a technique of gradually increasing the priority of the waiting processes as time goes on (only for processes that are waiting for a long time). The aim of this process is to get the waiting process to a priority high enough to execute directly or execute via tiebrake using FCFS.
## 3.4 Round-Robin Scheduling (RR or RRS)
- Specifically designed for time-sharing systems.
- it is similar to FCFS but preemptuion is added to enable the system to switch between processes. A small unit of time, called a *time-quantum* is defined, generally from 10ms to 100ms.
- The Ready queue is circular FIFO queue where new process are added to the "tail" and the CPU goes around in circles to give each process 1 time quanta to execute the program.
- If the process has a CPU burst $\leq$ 1 time quanta it gets executed completely and terminates, if not, then context switch occurs and the process is placed at the tail then waits for CPU Scheduler to come around.
- The Performance of the RR algorithm depends heavily on the size of the time quantum. if it is too large, RR is basically equal to FCFS. if it is too small, it is called *'Processor Sharing'* which creates the appearance that each of the n processes has its own processor running at 1/n speed of a real processor.
- For ideal performance, we want the Context Switch Time to take <10% time of the time quantum so that <10% of the CPU time is spent on context switching. Modern OS have reduced this to around 1% - where Context Switch Time is 10 microseconds and Time Quanta between 10-100 milliseconds (i.e., 10,000-100,000 microseconds which is 100 times the CST)


==***Note: Multi-processor Scheduling is purely numerical in nature. No Theory. 
Use tutorial sheets wisely.***==

---
Next Chapter ---> [[Pipes\|Pipes]]
# Reference Material
1. "Operating Systems Concepts" 9th Edition - A. Silberschatz et. al
2. Video Number 31-55 of [Operating Systems Playlist - Neso Academy](https://www.youtube.com/playlist?list=PLBlnK6fEyqRiVhbXDGLXDk_OQAeuVcp2O)
3. From video 2.1 to 2.11 from [Operating Systems Playlist - Gate Smashers](https://www.youtube.com/playlist?list=PLxCzCOWd7aiGz9donHRrE9I3Mwn6XdP8p)

