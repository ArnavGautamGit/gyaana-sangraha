---
{"dg-publish":true,"permalink":"/Threads/","tags":["CompSci"]}
---

# Index/Contents
[[Threads#1. What are Threads?\|#1. What are Threads?]]
[[Threads#2. What is the difference between a Process and a Thread?\|#2. What is the difference between a Process and a Thread?]]

[[Threads#Reference Material\|#Reference Material]]

-----
# 1. What are Threads?
Thread is a basic unit of CPU utilisation
A Thread can also be defined as a process that can be divided into multiple light weight executable entities to parallelize the task.
- A single thread can perform only one task at a time.
- Multi-threaded processes can perform multiple tasks simultaneously.
- A 2-threaded process can perform a maximum of 2 tasks at the same time.
In a Multithreaded process, Code, Data and Files are shared across all threads whereas the Registers and Stacks are unique to each thread.

Each Thread has:
- Thread ID
- Program Counter
- Register Set
- Stack

---
# 2. What is the difference between a Process and a Thread?

| PROCESS | THREAD |
|--------|---------|
| For the same data and code, needs new memory location and registers | Uses Common data and files, but has unique stack Address location is the same |
| Independent | Dependent |
| Needs to attach to a process | It can live independently and has at least 1 thread.|
| Number of Threads $\nleq$ Number of Proceses | Number of Threads $\geq$ Number of processes |
| Has System Call feature | No System Calls |
| If a process dies, all its threads die | If a thread dies, stack is reclaimed |
| Different process, different pid, code, data etc. | Different threads can share same copy of Code and Data |
| Blocking a process does not kill the thread. | Blocking a thread can kill the process (in single-threaded systems)|
| Context Switching Slower | Context Switching *fasterrrr* |

Note: Simgle-thread is also called a Kernel-Level thread. 

---
Next Chapter ---> [[Inter-Process Communication\|Inter-Process Communication]]
# Reference Material
Slides and in general class notes that I copied down for the first 2 topics.
Ma'am quoted a different source in the slides: [Columbia Education](https://www.cs.columbia.edu/~jungfeng/13fa-w4118/lectures/108-thread.pdf)

