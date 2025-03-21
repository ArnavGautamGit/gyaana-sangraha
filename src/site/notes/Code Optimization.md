---
{"dg-publish":true,"permalink":"/Code Optimization/","tags":["Academics","Software-Development"]}
---

# Index/Contents
[[Code Optimization#What is Code Optimization?\|#What is Code Optimization?]]
[[Code Optimization#Footnotes\|#Footnotes]]

-----
# What is Code Optimization?
Modifying the code so that the software works more efficiently or with fewer resources is known as Code Optimization.
It can broadly classified into 2 types:
1. ***Platform Dependent***: These techniques depend on the individual platform and Operating System since it fiddles with things like instruction-scheduling, cache optimization techniques etc.
2. ***Platform Independent***: These techniques are platform/OS independent such as: reduction in function calls, reduction in conditions, memory efficient routines etc.

## The Levels of Code Optimization
1. ***Design Level*** - Design of Software is changed to be more efficient
2. ***Source Code Level*** - Source Code is optimized
3. ***Assembly Level*** - Assembly language specifically designed for this
4. ***Run-time Level*** - JIT Compilers can make run-time adjustments in code {[[Basics of Computer Architecture#^compilers\|Basics of Computer Architecture#^compilers]]}

## Reasons for Code Optimization
1. Avoid Redundancy - do not calculate something that already has been calculated
2. Smaller Code - easier on the CPU and Memory
3. Increases Locality of Refernece since code is executed closer together and stored together.
4. Reviewing code reveals insights which can aid in optimization, debugging and further development.

## Criteria for Code Optimization
1. Must preserve semantic equivalence of programs
2. Algorithm must not be modded
3. Transformation on average should speed up the execution of the program. They are generally simple enough to have a good effect.
4. Worth the effort - the extra time and effort spent on optimization should be a significant improvement

# Peephole Optimzation
Sub-optimal sequence of instructions that match a known pattern are transformed into optimal sequences of instructions.
Works by sliding a window of several instructions - called a peephole.

Techniques of Peephole Optimation:
1. ***Compile Time Evaluation*** - expressions whose values are pre-computed at the compilation time. Constant folding {see [[Code Optimization#^1\|#^1]]} and Constant Propagation {check [[Code Optimization#^2\|#^2]]}
2. ***Common sub-expression elimination*** - Identify common sub-expression in different expressions, compute once and use results everywhere else. iT is done by breaking it into 3-Address Code. Global elimination is done on flow graph.
3. ***code motion*** - moving code from one part to another without changing the algorithm. Reduces code size and execution frequency. Example: Move expression out of loop if it does not affect the loop.
4. ***strength reduction*** - replace the operator of higher cost with a lower cost one. Example: use repeated addition instead of multiplication.
5. ***dead code elimination*** - remove useless code that does not add shit.
6. ***copy propagation*** - if one variable is declared equal to another. Given neither of them are changed, the other variable can be used in place of the original. results in smaller code.
7. ***loop optimization*** - if there are nested loops, decrease the instructions in loop condition of the innermost loop. Done using Code Motion and Strength Reduction. 

 All in all, Peephole Optimization is very fast as there is small overhead per instruction since they use a small fixed-size window.
 It is often easier to generate shit code and peephole optimize it than generate good code in first try.

# Code Refactoring
***Definition***: Rearranging & Restructuring the code in order to make code easy to maintain and modify.
- Not Arbitrary Restructuring
- Many Techniques exist
- One must refactor whenever we see a better way to do things or we can do so without breaking the code
- One must never refactor someone else's code without permission or code that is already stable that would not need to change.
- Code that must be refactored is also called code with "bad smell"
	- duplicate code
	- long methods
	- big classes
	- big functions
	- big switch statements
	- long navigations
	- lots of checking for null objects
	- un-encapsulated fields
- Encapsulated Classes are those which do not have public variables. variables and objects are provate but their GET functions are public.
- Refer slides

# Coding Standards and Guidelines
## Reasons
- It gives uniform appearance to code written by different engineers
- Enhances COde understanding
- Encourages good programming practices

## Header Standards
Header should contain:
- name of module
- date of creation of module
- author name
- modification history
- synopsis of module
- different functions supported (along with input/output)
- global variables accessed/modified by module
## Code Guidelines
- Simple coding style which is never too clever nor too difficult to understand.
- Avoid obscure side effects of fucntion calls, call-by-reference, modification of global variables etc.
- Do not use the same identifier to denote several temporary entries
	- variables must have descriptive, meaningful names
	- use variables for multiple purposes
- Code must be well documented
- Length of any function should not be $\gt$ 10 lines
- Do not use goto statements, they make code look unstructured and even amateur-ish.

## Code Review
It is carried out for each module that has been made and optimized to check if all syntax errors and ither errors have been solved and to check that optimization process has not removed functionality or induced new bugs in the system. They are extremely cost-effective strategies to reduce errors and produce high-quality code. They are of two types: Code Walkthroughs and Code Inspections.
### Code Walkthroughs
- informal technique
- few members of dev team are handed code a few days before tghe meeting to read & understand.
- Each member selects a few test cases and simulate execution of code.
- main objective is to discover algorithmic and logical errors in the code.
- everyone notes their findings to discuss in the meetings.
- Team size should be not too small not too big, close to 3-7 members.
- Discuss only the errors and not how to fix them.
- to foster cooperation and avoid the engineers feeling they are being evaluated, managers should NOT attend the walk through meeting.

## Code Inspection
- formal technique
- used to discover common types of errors caused due to oversight and improper programming, also the check adherance to coding standards.
- big companies collect stats regarding different kinds of errors committed by the company employees
- Common errors seen in inspections
	- use of un-initialised variables
	- jumps into loops
	- non-terminating loops
	- incompatible assignments
	- out of bounds array indices
	- improper storage allocation/deallocation
	- uyse of incorrect logical operators
	- improper modification of loop variables

---
Next Chapter --->[[Haalstead's Software Metrics\|Haalstead's Software Metrics]]
# Footnotes
1. It aims to reduce the number of expressions and constant values.
{ #1}

2. it is better if we replace the variable with a constant it was assigned earlier wherever possible
{ #2}



