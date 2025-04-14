---
{"dg-publish":true,"permalink":"/Software Testing/","tags":["CompSci","Software-Development"]}
---

---
# Software Testing
> Testing is a process to test whether the provided solution runs correctly & efficiently as intended without throwing any errors.

It can also be defined as:
> A process of excuting a program with the intent of finding errors.

Most big Multi-National Companies operate a separate testing wing for Software Testing which test the following:
1. All possible inputs whether valid or invalid
	1. Valid inputs must give valid output.
	2. Invalid input must give invalid output.
2. Logic Errors
3. Boundary Value Performance

## What is a Bug, Error, Fault or Failure?
A Bug is a mistake in the code made by the programmer.
An error is the reflection of that mistake on the terminal.
A fault is a mistake in the [[ER diagram\|ER diagram]] or Class or Sequence or other diagrams - which if occuring in the software would lead to failure! A failure in general is defined as a point or event in Software which makes it fail to stick to (or fulfill) its objective.

---
# Types of Software Tests
1. ***==Alpha Tests==***: Performed by Developers/testers on their end.
2. ***==Beta Tests==***: Performed by users on the users' end.
3. ***==Functional Tests==***: Input Daalo, Output Nikaalo - also called "[[Black-Box Testing\|Black-Box Testing]]".
4. ***==Structural Tests==***: Complementary approach to Functional Tests - used to check if the structure of the code is efficient or if the code needs restructuring.
5. ***==Path Testing==***: Using Flow Graphs and applying [[McCabe's Software Metrics\|McCabe's Software Metrics]].

---
# Methods of Software Testing
Any software is tested based on one of the following methodologies:
1. Boundary Value Analysis
2. Robustness Testing
3. Worst-Case Testing
4. Equivalent Class Testing
5. Decision table based Testing

## Boundary Value Analysis (BVA)
Every variable has a domain of accepted values beyond which it should not accept input or at least not give a valid output for invalid input. Boundary value is at the edge of the domain. If we take two values of variables a & b their domains can be displayed on x & y axes as a rectangle.
A Boundary value is a value on (or very close to) the edge of this rectangle.

***==Test Cases must NOT repeat==. Each case must be unique.***

> #### How to find Boundary Values?
> Find Groups or pairs of variables on the boundaries on tghe graph by fixing the value of one of the variables at the centre of its domain and alternating the other values from minimum, minimum + 1, middle/centre, maxiumum -1 & maximum.
> Do the same for the other side as well.

## Robustness Testing (RT)
This is to go one-step beyond the BVA. We considered two extra cases for each variable that are just one step OUTSIDE the domain i.e., minimum - 1 and maximum + 1.
This is done to check if invalid values gives a valid reply.

Just like BVA, ***Test Cases should NEVER repeat***.

According to BVA, we have $\large 4n + 1$ test cases,
Here we have 2 extra test cases for each $\large n$ hence, the total number of test cases is: $\large 6n + 1$

## Worst-Case Testing (WCT)
We need to check if there are more than one variables have extreme values. We check for the absolute worst cases that are possible.
It generates $\large 5^n$ test cases for $\large n$ variables.

## Equivalent Class Testing (ECT)
An equivalent class is a class/set which has similar functionality & time complexity. 
Classes have been made to represet a specific type of input.
Explore further from YouTube.

> ***==Note==***: Unlike BVA & RT, Test cses repeating in Equivalence Class Testing is not a big deal since it is aimed at reducing the number of test cases while keeping up the thoroughness of testing like the other methods.

In this method, we need two things to implement this:
1. ***Knowledge of Programming***: if there is a variable of range 1 to 10, then one class is valid class i.e., $\large 1\lt i \lt 10$, and there are two invalid classes: $\large i \gt 10$ and $\large i \lt 1$. Understanding how variables are defined, what is their range in which they should give the intended valid output and then crafting a class accordingly requires some knowledge of programming concepts.
2. ***Making/Choosing Test Cases***: The next step is to test the classes, which is done using Equivalence classes, first we take the valid class and build as many test cases on the class as possible in phase 1 of testing. In phase 2, we go for the invalid classes, although we do keep some cases from valid classes but we makle sure to add at least 1 case from each invalid class to check if valid output is given invalid input values.

## Decision Table based Testing
It is a type of [[Black-Box Testing\|Black-Box Testing]].
Used when a vareity of actions exist and we need to take a particular action depending uponthe existing condition.
![Decision Table Format.png](/img/user/Vaulted%20Images/Decision%20Table%20Format.png)

Similarly,
When we test a program which is made to input three numbers and check if there are the seides of a triangle or not, we have this table:
![Decision Table 1.png](/img/user/Vaulted%20Images/Decision%20Table%201.png)
 
Here, the action stub of "Impossible" has been added, since the condition isn't possible but that doesn't mean we are not supposed to test it. Since invalid values are also to be tested.

The condition "is a side of a triangle" is the Entry Condition, which if false is of no effect to us (outside of our testing domain) since we are not the kind who strive to prove the side of a Cube as a side of a Triangle ;p

> ***==Note==***: Sometimes, we may see the conditions/user using Y/N instead of T/F.
> It is alsoto be noted that Decision Tables are regarded as the best asset for testing since they allow bug-fixing without actually having to run the code. 

This is heavily connected with CEG Technique.
## Cause & Effect Graphing Technique (CEG Technique)
It is a technique which is used in conjunction with [[Software Testing#Decision Table based Testing\|#Decision Table based Testing]] to select a high yield set of test cases.
It points out the incompleteness and ambiguity in specifications.

This topic is very similar to what we learnt in Concepts of Graph Theory - a very simple application of [[Colouring & Applications\|Colouring & Applications]]
#### How are test cases derived?
1. Identify the cause & effect from the specs & assign unique numbers to each of them.
2. Draw a boolean graph linking cause & effect.
3. Specify constraints on graph describingin the combs of cause and/or effects that are impossible
4. Convert graph into limited entry decision table by tracing the straight edges in the graph.

> ***==Note==***: Here, in this context:
> ***Cause*** is any distinct input condition or its equivalence class. 
> ***Effect*** is any output condition or system transformation (i.e., change that occurs in the system)

#### Graph Notation for Cause & Effect Graphing
![CEG1.png](/img/user/Vaulted%20Images/CEG1.png)

---
Next Chapter --->[[COCOMO Model\|COCOMO Model]]
