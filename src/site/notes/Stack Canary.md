---
{"dg-publish":true,"permalink":"/Stack Canary/","tags":["Academics","Software-Development","CyberSec"]}
---


---
# Stack Canary
> A number placed between User Data and Return Address in the stack, so any overflow in the user data would first overwrite the canary before getting to the return address, which will allow the system/app to catch [[Stack Overflow\|Stack Overflow]] conditions on its own since the system first check Stack Canaries to see if they have changed.

Stack Canaries are an important layer of prevention which is very similar in principle to Checksum implemented in [[Transmission Control Protocol (TCP)\|TCP]] and [[IPv4 Addressing\|IPv4 Addressing]].

It is generally a very small integer whose value has been chosen at random at program start & it is then placed in the memory, just before the stack pointer (or return address).

Some tools used for this purpose:
1. ARCHER
2. BOON
3. Polyspace C Verifier
4. SPLINT
5. UNO
among others...

All the tools also have a possiblity of false alarms - generally this probability seems to scale with the efficiency of detecting Stack Overflows.

---
# Footnotes