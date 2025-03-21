---
{"dg-publish":true,"permalink":"/Introduction to OS/","tags":["Academics"]}
---


# Index/Contents
[[Introduction to OS#1. What is an Operating System?\|#1. What is an Operating System?]]
[[Introduction to OS#2. Components of an Operating System\|#2. Components of an Operating System]]
[[Introduction to OS#3. Types of Operating System\|#3. Types of Operating System]]
[[Introduction to OS#Reference Material\|#Reference Material]]

-----
# 1. What is an Operating System?
An Operating System - also called as an OS, is a program that acts as a bridge between the user and the hardware. It manages Computer Software and Computer Hardware and grants common services for computer programs

---
# 2. Components of an Operating System
1. Hardware Devices ==**(outermost layer)**==
2. Device Drivers
3. File Systems
4. User Interface
5. API
6. Kernel ==**(innermost layer)**==
## 2.1 What is a Kernel? 
It is the innermost layer (or Central layer) of an Operating System.
It is supposed to manage the operations of the program (the OS and Softwares) and the Hardware, help them work in Synergy.

*Real World Analogy*: Think of the Road being a OS, there is a two sides on a road (you cannot go onto the wrong side in oncoming traffic) then the level and kind of traffic on a road is like a Kernel. The Hardware device is the car and the device driver is the driver of the car. Now keep reading to see how the API and File Systems fit.
## 2.2 Types of Kernel
1. **Micro-Kernel** - Contains Basic function
2. **Monolithic Kernel** - Contains many device drivers.
3. **Hybrid Kernel** - Combines the aspects of 1 and 2.
4. **Exo-Kernel** - Contains Hardware Resources to applications through high-level abstraction.
5. **Nano-Kernel** - Contain Hardware Abstraction without System Services
## 2.3 API - Application Program Interface
It is a set of routines, protocols and tools for building softwares and applications (apps).
it allows for use of applications or part of its functions to integrate with other apps as well.
Apps cannot access each other's data directly since apps are propreitery tech.... and they need to keep them safe.
APIs act as a secure channel of conversation, the API is a security layer + delivery agent who only delivers the data to the requesting app that it is programmed to deliveer or data it deems secure to deliver. (According to the programmers which program it)
APIs are always attack-tested by Cyber-Security Analysts - using Python and JavaScript.
In the above stated analogy, API is like a security camera at Traffic Signals.
## 2.4 File Systems
A Data Structure used by the OS to keep track of files. Undertand them to be similar to the lane system on roads.
## 2.5 Device Driver
Driver of a Harware Device, which establishes connection between the device and the OS and works as an interpreting program between the two... Using the Car and Road analgy, a car cannot move without its driver!
## 2.6 Hardware Device
Keyboard, Mouse, Monitor, Printer etc.
Car that runs on the road...

---
# 3. Types of Operating System
## 3.1 Batch System
-  Many jobs are punched on a punch card and given to the Operator
- Jobs are completed one-by-one.
- Output only provided when all jobs are complete
**Disadvantage: No user-computer interaction and No Prioritization.**

## 3.2 Multi-Programming System
- More than one program gets executed at once
- CPU never sits idle
**Objective is to maximize CPU usage**

## 3.3 Time-Sharing System
- Logical expansion of the Multi-programming one
**Objective is to reduce response time**

## 3.4 Multi-Processor System
- Two or more processors in close commuication i.e in the same CPU with a common bus, Clock  and Memory.
- Such 1 processor is seldom called a "core" by companies like Intel, a "quad-core" means 4 processors.
- If you have n processors, you can do n processes together - like 2 processors can play songs and surf the web together...
- ==Also called a "Parallel System"==

**Advantages**: 
1. **Increased [[Throughput#Throughput in Process Scheduling\|Throughput]] (More input = more output)**
2. **Ability to scale-up the technology**
3. **Better Reliability.**
Symmetric ones have shared memory but Asymetric ones don't (they use Master-Slave strategy)

## 3.5 Real-Time System
- Uses Maximum time and resources for exact output and on-time result.
- Used for Automatic systems: like Auto-pilot and e-Commerce Apps.
- Two Types exist:
  1. Soft RTS - less strict execution time and accuracy
  2. Hard RTS - *EXACT* execution time and result.

## 3.6 Distributed System
Collection of Autonomous Computers linked by Computer hardware and equipped with Distributive System Software.
They Communicate by passing messages around

**Advantages:**
1. **Resource-Sharing
2. **Hextero-geneity
3. **Concurrency
4. **Sealability
5. **Transparency

---
Next Chapter ---> [[Process Concept\|Process Concept]]
# Reference Material



