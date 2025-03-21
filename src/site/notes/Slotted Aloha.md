---
{"dg-publish":true,"permalink":"/Slotted Aloha/","tags":["CompSci","CompNet"]}
---


---
# Slotted Aloha Random Access Protocol
Very Similar to [[Pure Aloha\|Pure Aloha]] but to slightly improve the problem Aloha encountered, it is going to make a small change.

The same protocol instead of being random is given time slots by plotting the time taken to transmit a message & plot it on the graph where y-axis is the list of senders & x-axis is time slots. Each slot is homogenous in length.

Data can be transmitted only at start of a slot. If the channel is empty and say A fires at t=0+2ms, B will not be able to fire until at the beginning of the next one. If a collision occurs, any random future time slot is picked to retry.

***==Throughput==***: 36.84% (double of Pure Aloha's)

***==Problem==***: The fight is now [[Process Scheduling#3.1 *First-Come, First-Served Scheduling (FCFS)*\|First Come, First Served]] based and it is not the best thing technically. Since now if both of the senders are sending together, they will be met with the fact that it is but whoever has a faster propagation time will win... or you have a collision just like Pure Aloha.

---
# Footnotes