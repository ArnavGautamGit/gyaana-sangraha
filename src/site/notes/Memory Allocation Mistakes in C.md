---
{"dg-publish":true,"permalink":"/Memory Allocation Mistakes in C/","tags":["Academics","coding","Software-Development"]}
---


---
# Memory Allocation Mistakes in C
> Mistakes that are easy to make (and are commonly made) if one is allocating memory using C Language.

1. Failing to check Return Values
2. Referencing Freed Memory - no output since its empty.
3. Freeing Memory more than once - redundant steps and time waste.
4. Error in computing size for dynamic array - [[Array Overflow\|Array Overflow]] can occur.
5. Failing to free allocated memory - can cause [[Memory Leak\|Memory Leak]] i.e., vulnerable to [[DOS Attack\|DOS Attack]] 


---
# Footnotes