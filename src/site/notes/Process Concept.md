---
{"dg-publish":true,"permalink":"/Process Concept/","tags":["CompSci"]}
---


----
# Index/Contents
[[Process Concept#What is a Process?\|#What is a Process?]]
[[Process Concept#What are the various states of a process?\|#What are the various states of a process?]]
[[Process Concept#What are the various states of a process?\|#What are the various states of a process?]]
[[Process Concept#What is a Process Control Block(PCB)?\|#What is a Process Control Block(PCB)?]]
[[Process Concept#Various Operations possible on a Process\|#Various Operations possible on a Process]]
[[Process Concept#How do these Processes communicate with each other?\|#How do these Processes communicate with each other?]]
[[Process Concept#Reference Material\|#Reference Material]]

-----
# What is a Process?
A Program or one of its portions/instances being executed in the processor at a given time is known as a process. Sometimes Processes are known as *Jobs* as well.
Each process has:
- A Current State
- A set of system resources needed to run it.
***It is important to note that not all programs are processes, only the active part of a program being run can be called as a process.***

---
# What are the various states of a process?
1. New: A process is just made
2. Waiting: The process is waiting to be executed
3. Ready: The process is ready to be executed
4. Running: The process is being executed
5. Terminated: The process has finished execution. (The process has been executed)

---
# What is a Process Control Block(PCB)?
Also known as Task Control Block or TCB, it contains valuable information about the program which makes it unique and identifiable.
It is also responsible to be able to identify a process, play or pause its execution.
It stores process specific information, like:
- ***==State==***: State of a process can be ready, waiting, running, etc
- ***==Program counter==***: It stores location of next instruction to execute
- ***==CPU scheduling Info==***: it provides relative priorities of process and pointers to queue
- ***==CPU registers==***: It stores information/ data associated with process
- ***==Memory Info==***: Starting Address and size of process.
- ***==Usage Info==***: Turn Around Time and CPU usage. (aka Accounting Info)
- ***==Identifier==***: Each process has a unique ID - called as pid.
- ***==Priority==***: Does it have a higher priority than others?

---
# Various Operations possible on a Process
There are various operations possible, for example:
1. Process Creation
2. Process Termination
These are two of the most basic ones. Operations beyond these are technically out of syllabus and will make these notes too long.
## Process Creation
A Process can create multiple processes with create-process system call during execution.
The creating processes are called Perent Processes and the new processes are known as the children processes. Once a child process is made, its identifiers are transferred to the parent process.
The Child Processes may create their own processes - forming a tree of processes.
On UNIX, we can easily get the list of processes by using the ps command.
Please check [[Process tree in Solaris.jpeg]] to see how a Process creation tree works/looks like.

When a process creates a new process, two main possibilities exist in terms of execution:
1. The parent continues to execute concurrently with its children.
2. The paret waits until some or all of its children have finished execution.

There are two possiblities in terms of address space of the new processes:
1. The child process is a duplicate of the parent process (same program and data as parent)
2. The child process has a new program loaded into it.
## Process Termination
A Process terminates when it asks the OS to delete it after it has executed the final statement of its program using the exit() system call.
If this specific process has a parent process, it may return the output value (if any) to its parent using the wait() system call. The ouput value is generally is an integer in binary.
All the resources held by the process (physical + virtual memory, I/O buffers, open files etc.) are all deallocated by the OS.
A process (generally the parent process) can cause the termination of the other process by invoking the correct command.
A parent may terminate the execution of one of its child processes for these 3 main reasons:
1. If the parent process can inspect the child's state, then the child may be terminated for exceeding the resources allocated to it.
2. The task assigned to the child is no longer required.
3. The parent is exiting, and this specific OS does not allow a child to work if the parent terminates. (Example: Certain VMs)
The phenomenon of all child processes of a parent process being termnated since the parent is getting terminated (due to limitations on the side of the OS) is known as ==***Cascading Termination***==.

---
# How do these Processes communicate with each other?
The situation of two or more processes being able to cooperate calls for "Inter-Process Communication" also called IPC (check [[Inter-Process Communication\|Inter-Process Communication]] for more detailed explanation). IPC gives a mechanism to share data and info.

Any process that does not share data, affects or gets affected by another process is known as an independent process.
Any process that shares data with another is a cooperating process.

---
Next Chapter ---> [[Process Scheduling\|Process Scheduling]]
# Reference Material
1. Video Number 15-31 from [Operating Systems Playlist - Neso Academy](https://www.youtube.com/playlist?list=PLBlnK6fEyqRiVhbXDGLXDk_OQAeuVcp2O)
2. "Operating Systems Concepts" 9th Edition - A. Silberschatz et. al
