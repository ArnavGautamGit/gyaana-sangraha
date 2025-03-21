---
{"dg-publish":true,"permalink":"/Inter-Process Communication/","tags":["Academics"]}
---


-----
# What is Inter-Process Communication (IPC)?
The situation of two or more processes being able to cooperate calls for "Inter-Process Communication" also called IPC. It gives a mechanism to share data and info.

Any process that does not share data, affects or gets affected by another process is known as an independent process.
Any process that shares data with another is a cooperating process.
## Reasons/Need of Inter-Process Comms?
1. ==***Information Sharing***==: Need for concurrent access (for multiple users) to the same files.
2. ==***Computaion Speedup***==: Task broken into sub-tasks - when each subtask is handled in parallel, Computation gets faster than before.
3. ==***Modularity***==: Helps in organising the system into separate processes and threads.
4. ==***Convenience***==: Helps in cases when the user is multi-tasking.
## Various Models of IPC
There are only 2 models of Inter Process Communication (IPC)
1. Shared-Memory Systems
2. Message-Passing Systems
### Shared-Memory Systems
Step-by-step guide to how Shared-Memory System Works.
- Processes have a shared memory region between them
- Process "A" wishes to communicate to Process "B", so A creates the SMR.
- SMR resides in the address space of A.
- To read from the SMR, other processes must also attach the SMR to their address space.
- In this example, we have assumed no other processes are taking place, but even if there was a new process, Process "C", it would still require to attach SMR to its address space.
- Process "A" communicates to Process "B" by writing the data to the Shared Memory Region.
- Process B now reads from the SMR.
Communication is achieved via an intermediary.

Some more things to note:
1. Normally, the OS does not allow B to read A's memory directly or vice-versa.
2. Shared-Memory needs at least 2 or more processes agree to point 1.
#### Concept of Buffers in Shared-Memory Systems
The Shared-Memory Region (SMR) is seldom called as a Buffer to make it simpler to understand the concept.
There are two kinds of Buffers:
1. ==***Bounded***==: Limited/Fixed buffer size (buffer can get full) Process "A" must wait if buffer is full and Process "B" must wait if buffer is empty.
2. ==***Unbounded***==: Unlimited Size. Hence "A" doesn't need to wait, (since buffer will never get full) but "B" has to wait if the buffer is empty.
## Message-Passing Systems
Message-Passing provides a mechanism to facilitate IPC without sharing Address Space in Memory.
Step-by-step guide on how it works:
- It uses the Kernel to communicate between 2 processes.
- Process 'A' sends the data/info as a message to the Kernel.
- Kernel forwards that message to Process 'B'
- Process 'B' can now read the data/info shared by 'A'.
### Why is it needed?
It is particularly useful on Computer Networks, where there are multiple computers connected to a server where information is stored and multiple processes on multiple computers are trying to access different informatuion from the server. Whereas, the Shared-Memory method is used on processes running on 1 computer.
### What functionality does it provide to facilitate IPC?
it provides mainly 2 operations to facilitate IPC:
- Send Message
- Receive Message
Message sent by the MPS can be of two types,
1. ***Fixed Size***: Straightforward Implementation, hard to code.
2. ***Variable Size***: hard to implement, easy to code.
### Communication Link Concept
For process A and B to communicate with one another, we need a link between them, this link may or may not be physical. Here, we will talk of the logical link first.
There are multiple ways to implement this:
- ***Direct and Indirect communication***
- ***Synchronus and Asynchronus communication (Blocking and Non-Blocking)***
- ***Automatic or Explicit Buffering***
There are several issues related with these known as Naming, Sychronisation and Buffering respectively.
### Issues in Message-Passing Systems
##### ==***Issue 1(A): Naming (in Direct Comms)***==
Symmetry/Asymmetry in Addressing offers limited Modularity (changing an identifer for one process may require to go through every single process definition... in simpler terms - its a hassle). How Direct Comms work:
- Found in Direct and Indirect Communication method.
- Commands like `send();` and `receive();` need to specify who is the sender/receiver like
  `send(B, message);` for sending 'B' the message named 'message'.
  `receive(A, message);` for receivinig message from 'A' which is named 'message'.
- ==*Symmetry* in Addressing==: A link between processes is established automatically but they must know their identity (name) to communicate and both processes must identify the other in the commands.
- A link is associated with exactly 2 processes and between each pair of processes, there can only exist one link.
- ==*Asymmetry* in Addressing==: Some variants may have only the sender specify the name, whereas the receiver only specifies the id.

##### ==***Issue 1(B): Naming (in Indirect Comms)***==
How Indirect Comms work:
- The messages are sent to and received from mailboxes (or ports)
- One Link, One Mailbox: *One link corresponds to one mailbox only*
- A link is established if both the processes have a shared mailbox
- Theoretically, multiple processes can go on the same link but it creates a problem.
- **Problem**: *If one process P1 sends a message but two processes P2 and P3 respectively send the `receive();` command then who gets the message? P2? P3? or both?*
- To avoid the above problem, associate only 2 processes at maximum with the same link (P1-P2 and P1-P3 go on two separate links)
- Also, allow only one process to use the `receive();` operation at a time.
- The System should be allowed to select which process should get the message either arbitrarily select one (but not both) or algorithmize it. (see [[Process Scheduling\|Process Scheduling]])
- Any Mailbox may be owned by the process or the OS. Process-owned mailboxes are easier to operate as the above problem can never exist, but hard to program since as soon as the process terminates, the mailbox disappears.
##### ==***Issue 2: Synchronisation***==
Synchronisation Problem occurs in both Blocking (Synchronous) and Non-blocking (Asynchronous):
1. ***Blocking Send***: The sending process is blocked until message is received by the receiving process or mailbox
2. ***Non-Blocking Send***: The sending process sends mesage and resumes operation.
3. ***Blocking Receive***: The receiver blocks until a message is available.
4. ***Non-blocking Receive***: The receiver receives either a valid message or null.
There are multiple combos of `send();` and `receive();` commands possible. When both send and receive are blocking in nature, we get ***rendezvous*** between the sender and receiver.
##### ==***Issue 3: Buffering***==
Whether communication is direct or indirect, messages exchanged by communicating processes are stored in a queue. That queue is somtimes called as the Buffer Queue. 
They can implemented in 3 ways:
- ***Zero Capacity***: The queue has a maximum capacity of Zero; no buffering is allowed; must use Blocking Send.
- ***Bounded Capacity***: The queue has finite length 'n'; thus at most 'n' messages can stay. If space is available, Non-Blocking Send; If buffer is full, Blocking Send.
- ***Unbounded Capacity***: The queue is infinite; Non-blocking Send always.

---
# What are Sockets, then?
A *socket* is defined as an endpoint for communication. A pair of communicating processes use a pair of sockets - one for each process.
A socket is identified by an IP address concatenated with a port number.
Sockets are generally used for communication in Client-Server Systems.
Refer to [Sockets in OS](https://youtu.be/uagKTbohimU?si=ADyW5ki5zzaZpsaa) video by Neso Academy.

---
# What are Remote Procedure Calls?
Due to being Short on time, I don't have enough time to cover everything in these notes, just refer to the videos mentioned below to learn the topic. Have to watch this video again and again everytime revision is required.
[Remote Procedure Calls](https://youtu.be/QmhTjsOOrlw?si=7U3TRnVHVLGBFVcq)
[Issues with Remote Procedure Calls and how to fix them](https://youtu.be/jH3RezOHROU?si=LslvKyJZDzGOP88M)

---
Next Chapter ---> [[Deadlocks\|Deadlocks]]
# Footnotes


