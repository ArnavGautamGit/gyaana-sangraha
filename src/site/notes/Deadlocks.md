---
{"dg-publish":true,"permalink":"/Deadlocks/","tags":["Academics"]}
---

###### Created on: 26/09/2023
###### Last updated: 26/09/2023

----
# Index/Contents
[[Deadlocks#1. What are Deadlocks?\|#1. What are Deadlocks?]]
[[Deadlocks#Reference Material\|#Reference Material]]

-----
# 1. What are Deadlocks?
A Deadlock is defined as a situation where a waiting process is never again able to change state, because the resources it has requested are held by other waiting processes (which may be waiting due to the same reason). $^{[1]}$
## 1.1 Some things to note
A process can only use any resource after the request of using the aforementioned resource is accepted and the resource has been assigned. Obviously, a process cannot request for a number of resources greater than the number of resources available. i.e., A process cannot request for 3 printers if the system only has one.
## 1.2 Necessary Conditions for Deadlocks
Conditions that need to hold simultaneously in the system for a deadlock to occur.
1. ==***Mutual Exclusion***==: At least one resource must be held in a non-sharable mode; i.e., only one process should work at a time (on a specific resource).
2. ==***Hold and Wait***==: A prtocess must be holding a non-sharable resource and be waiting for another resource (held by other processes) to finish before it can release the control of this one.
3. ==***No Preemption***==: Resources cannot be preempted. i.e., a resource cannot be released by a process until the task which utilizes the resource has completely finished.
4. ==***Circular Wait***==: A series of waiting processes must exist such that $P_0$ is waiting for a resource which is currently held by $P_1$ as $P_1$ itself waits for a resource held by $P_2$ and so on.
## 1.3 Resource Allocation Graph
Check Pages 288-289 of the book $^{[1]}$ to see the graph.
- If graph has no cycles, none of the processes are deadlocked. If there is a cycle, a deadlock ***MAY*** or ***MAY NOT*** exist.

---
Next Chapter ---> [[Process Synchronisation\|Process Synchronisation]]
# Reference Material
$^{[1]}$ Operating Systems Concepts - Abraham Silberschatz et. al. (J128 LRC section 5.43)

