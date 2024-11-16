---
{"dg-publish":true,"permalink":"/CSMA/","tags":["Academics","CompNet"]}
---


---
# CSMA - Carrier Sense Multiple Access
Description in one line: 
> Check before transferring data if there is empty space.

Collisions happen due to Propagation Delay. (as established in [[Slotted Aloha\|Slotted Aloha]])
Hence, Vulnerble Time = Propagation Delay

There are three kinds based on Probability:
1. 1-persistent ---> Probability of message reaching without collisions is 1 i.e., empty channel.
2. p-persistent ---> Probability of message reaching without collisions is p
3. 0-persistnet ---> Probability of message reaching without collisions is 0 i.e., filled channel.

> Note: 0-persistent is also called "Non-persistent"

### How does Zero-Persistence work? (Non-Persistent CSMA)
Each sender in the network has probaility of p, there is a master probability which the Network Admin sets. The prabability acts as a priority - any value of p which is lower than master shall not be allowed to hold communication.

### Improved Protocols?
CSMA had researchers trying to evolve it into two different directions: [[CSMA-CD\|CSMA-CD]] and [[CSMA-CA\|CSMA-CA]] depending upon Collision Detection & Collision Avoidance

---
# Footnotes