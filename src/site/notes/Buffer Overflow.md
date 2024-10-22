---
{"dg-publish":true,"permalink":"/Buffer Overflow/","tags":["Academics","Software-Development","CyberSec"]}
---


---
# Buffer Overflow
> Condition where data exceeds the size of [[Buffer\|Buffer]] and overflow into other memory blocks and overwrites them - creating faults.

This can be of both types - unintentional or intentional.
Also, since Buffers are a theoretical concept, when Buffers are implemented as a [[Stack (Data Structure)\|Stack]], an overflow in the stack is referred to as a [[Stack Overflow\|Stack Overflow]]. 
### Description and Cause
In programming, the last number in an array is preserved for the null pointer which indicates where the array has ended. If you input `char buffer[5]` then enter "Arnav", then either we need 6 size array or the "v" at the end will need to be skipped since that is where the null pointer will be, without which the "v" will overflow into surrounding memory blocks & has the potential to create massive faults in the program - possibly destroy it.

C is not a "safe" language since it is very low level and can directly manipulate individual memory blocks - we need to be very cautious how we use them.

There are functions which one needs to keep in mind.

### Controlled Injection
> A carefully crafted string iteded to cause a buffer overflow can also overwrite the return address to be a valid return address to another program - making it similar to [[SQL Injection Attack\|SQL Injection Attack]].

It is  a quite dangerous version of Buffer Overflow and until this was found, the severity of this vulnerability was very underrated.
### Prevention
- Avoid [[Dangerous C and C++ Functions\|Dangerous C and C++ Functions]].
- Follow [[Good Software Engineering Practices\|Good Software Engineering Practices]].
- Avoid [[Memory Allocation Mistakes in C\|Memory Allocation Mistakes in C]].
- Leave larger input space for arrays - just to count larger corner cases & to be safe.

---
# Footnotes