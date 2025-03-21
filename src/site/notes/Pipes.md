---
{"dg-publish":true,"permalink":"/Pipes/","tags":["CompSci"]}
---

# Index/Contents
[[Pipes#1. What are Pipes?\|#1. What are Pipes?]]
[[Pipes#Reference Material\|#Reference Material]]

-----
# Pipes
> A Pipe acts as a conduit allowing two processes to communicate.

It is one of the oldest/earliest form of [[Inter-Process Communication\|Inter-Process Communication]] developed in the early UNIX systems.

In implementing a Pipe, 4 issues must be considered:
1. Does the pipe allow uni-directional or bi-directional communication?
2. If two way comms is allowed, then is it half-duplex (one way data flow at a time) or full-duplex (both way simultaneous data flow)
3. Is it compulsory that the process must be parent-child for communicating?

There are 2 common types of pipes:
1. Ordinary
2. Named
## 1.1 Ordinary Pipes
A process writes to one end of the pipe, another process receives it on the other end of the pipe.
These Ordinary pipes are uni-directional and can only send data one way.
Ordinary Pipes also require a parent-child relationship. The process sending is the parent and the receiver is the child (generally).
If two way comms are needed, we need two pipes sending data in opposite direction.
Ordinary pipes in UNIX and Windows behave differently

| UNIX | Windows |
|----|----|
| Pipes are treated like special files of parent process.| Pipes are treated as ordinary files only parent can create |
| Simple `read();` and `write();` can be used on them. | `ReadFile();`  and `WriteFile();` need to be used instead. |
| Child process inherits pipe automatically with `fork();` call. | Windows needs programmer to specify if pipe needs to be created or not. |
| Child can also create its pipe to parent | Child cannot create pipe to parent. Child can create a pipe only if it has a child of its own |

## 1.2 Named Pipes
Ordinary Pipes cease to exist when the communicating process terminate.
Named pipes allow transfer of data between processes in a FIFO manner and synchronization of process execution. Use of a named pipe allows processes to communicate even though they do not know what processes are on the other end of the pipe.

| UNIX | Windows |
|----|----|
| Bidirectional and Full-Duplex | Can choose between Half-Duplex and Full-Duplex. |
| Made as a Filesystem | Made as a file inside root directory in NPFS$^{[1]}$. |
| Lasts as long as PC is up. | Volatile (removed after the last reference to them is closed). |

## 1.3 Difference between the two types

| *ORDINARY PIPES* | *NAMED PIPES* |
|----|----|
| Cease to exist once even one of the process complete and get terminated. | Exists as long as the system is up (UNIX) or as long as their last reference is not closed. They outlive the processes anyway. |
| Require Parent-Child relationship between processes. | Processes can communicate without knowing each other. |
| Cannot be used with Microsoft's SQL server | Can be used with Microsoft's SQL Server |
| Uni-directional Pipe: One-Way Dataflow | Bi-directional Pipe: Data flows both ways (available in both Half and Full Duplex) |

---
Next Chapter --->[[Threads\|Threads]]
# Reference Material
"Operating Systems Concepts" - Silberschatz, Abraham. (9th Edition)

# Glossary
$^{[1]}$NPFS = Named Pipe File System. It is a FileSystem in Windows. All Windows named pipes are stored inside this root directory as separate, individual files. 
