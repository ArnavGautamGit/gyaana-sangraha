---
{"dg-publish":true,"permalink":"/Evolution of Multi-Level Machines/","tags":["Academics","COA"]}
---


----
# Index/Contents
[[Evolution of Multi-Level Machines#WW2 Era - 1940s\|#WW2 Era - 1940s]]
[[Evolution of Multi-Level Machines#Post WW2 Era - 1951\|#Post WW2 Era - 1951]]
[[Evolution of Multi-Level Machines#Cold War Era - 1960s to 1970s\|#Cold War Era - 1960s to 1970s]]
[[Evolution of Multi-Level Machines#Late Cold War Era - 1980s\|#Late Cold War Era - 1980s]]
[[Evolution of Multi-Level Machines#Reference Material\|#Reference Material]]

-----
# WW2 Era - 1940s
The first ***digital*** computers built in 1940s had only 2 levels, the ISA level and the Digital Logic level (i.e., L2 and L0 in the modern computers)
All the programming was done in the ISA level.
All of the circuits were in the form of Logic Gates in Digital Logic Level.

| Pros | Cons |
|---|---|
|Digital means less fiddling with Analogue tapes.|Circuits were complex and unreliable due to Vacuum tubes.|

# Post WW2 Era - 1951
In 1951 Wilkes and a team of researchers came up with a 3-level computer design.
The new level has an unchangeable and built-in Interpreter level (modern L1 like microprogram).
The Microprogram executed the ISA level code by translating it for the Logic Level.

| Pros | Cons |
|---|---|
| More Reliable since less Vacuum tubes are used now | Limited Instruction set, much smaller than the ISA. |

# Cold War Era - 1960s to 1970s
Until the 1960s, the computer needed an Operator who could use Punched Cards in a certain sequence to pass commands. In the 1960s, with the advent of a program named as an "Operating System", researchers tried ways to reduce the need of this operator or at least make computing more user-friendly. Slowly OS programs became more and more complex and better.

In the same time, new features and programs were added to a new level... some of these were similar to the ISA, and some of it was completely different (like I/O programs). these instructions were called as Operating System Macros or Supervisor Calls - nowadays known as System Calls.

1960s and 1970s were called as the golden age of Microprogramming - the Microprograms started to get big and bulky... also *they became **==painfully slow==.***
Why did that happen? Because the researchers realised that integer arithmetic, floating point arithmetic and function-calls can also be included in the microprograms...
Furthermore, once machine designers saw how easy it was to add new instructions, they began
looking around for other features to add to their microprograms. A few examples of these additions
included:
- Features to speed up computations involving arrays (indexing and indirect addressing)
- Features to permit programs to be moved in memory after they have started running (relocation
facilities) 
- I/O interrupt signals, process switching, instructions for processing audio, image, and multimedia
files etc. 
Numerous other features and facilities have been added over the years, usually for
speeding up some particular activity leading to ***==The Era of Elimination of Micrprogramming==***

# Late Cold War Era - 1980s
The researchers of this time thought of shortening the microprograms/microcodes by directly implementing the functionality in logic gates since that field had become more advanced than before as well...
In a way, computing went back to the time of the WW2 but that was since the approach to computing was changing.
The idea of an Arithmetic Unit (early forms of the ALU) were being conceived of.
The approach to L1 (Control Level) changed and the new levels of L3 (Software) sstarted to be improved.
In 1983, we saw the creation and expansion of the L4 (Assembly Level) and L5 (Language Level) with the advent of Computer Programming languages like Java and C. (C was launched in 1983) 

---
Next Chapter in COA ---> [[Evaluating Performance of Computer Systems\|Evaluating Performance of Computer Systems]]
# Reference Material
Module 1 slides on Google Classroom

