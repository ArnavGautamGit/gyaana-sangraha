---
{"dg-publish":true,"permalink":"/Haalstead's Software Metrics/","tags":["Academics","Software-Development"]}
---

# Index/Contents
[[Haalstead's Software Metrics#What are Haalstead's Software Metrics?\|#What are Haalstead's Software Metrics?]]
[[Haalstead's Software Metrics#Footnotes\|#Footnotes]]

-----
# What are Haalstead's Software Metrics?
Haalstead's Software Science is an analytical technique to measure size, development effort and development costs of a software.
$$\Large n = n_1 + n_2$$
where, 
$\large n =$ vocabulary of program, $\large n_1 =$ number of unique operators, $\large n_2=$ number of unique operands
$$\Large N = N_1 + N_2$$
where,
$\large N =$ Program Length, $\large N_1 =$ Total occurances of operators, $\large N_2 =$ Total occurances of operands

Using the above formulae for Vocabulary and Program Length, we can calculate the following:
$$\Large Volume \ of \ Program = V = N \times log_2(n)$$
$$\Large Program \ Level = L = \dfrac{V^*}{V}$$
$$\large here, \ V^* = (2 + n_2^*) \times log_2(2 + n_2^*) \Rightarrow\ Potential \ Minimum \ Volume$$
$$\Large Difficulty \ Level = \dfrac{1}{L} = (\dfrac{n_1}{2}) \times (\dfrac{N_2}{n_2})$$
$$\Large Effort = \dfrac{V}{L} = D \times V$$
$$\Large Estimated \ Program \ Length =  \hat{N} = n_1log_2(n_1) + n_2log_2(n_2)$$
$$\Large Estimated \ Program \ Level = \hat{L} = (\dfrac{2n_2}{n_1})\times N_2$$
$$\Large Language \ Level = \lambda = LV^* = L^2V$$
# Rules to Consider:
1. Comments are ignored.
2. All hash directives such as `#include <iostream>` and other `#include` commands are ignored.
3. Function Declaration Statements are ignored.
	1. Function calls are considered opertors.
	2. Arguments in functional calls are considered operands unless operators are also present in the arguments since they will be counted separately.
4. All variables and constants are considered operands.
5. Global variables used in different modules of the same program are counted as multiple occurrences of the same variable.
6. Local Variables in different locations but with the same name are considered unique operands.
7. All the loop statements, switch cases and conditionals (if, else) are considered as operators.
8. All the reserve words such as "return", "break", "continue", "sizeof" etc. are considered as operators.
9. All bracket-pairs, commas and terminators unless inside quotes are considered as operators else the entire statement inside the quotation (`" "`) marks is considered as one single operand.
10. GOTO is counted as an operators but the label is an operand.
11. Assignment and Mathematical and Logical operators are considered as operators. Increment and Decrement operators (++ and --) are treated separate from addition (+) and subtraction (-) operators.
12. In array variables, such as `array_name[index]` the name of the array (here, `array_name`) and the `index` are operands whereas the square brackets are operators. Similarly in `struct_name -> member_name` only `->` is an operator.




---
Next Chapter --->[[McCabe's Software Metrics\|McCabe's Software Metrics]]
# Footnotes


