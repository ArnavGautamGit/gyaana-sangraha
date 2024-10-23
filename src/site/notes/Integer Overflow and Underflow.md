---
{"dg-publish":true,"permalink":"/Integer Overflow and Underflow/","tags":["Academics","CyberSec","Software-Development"]}
---


---
# Integer Overflow and Underflow
> ***Integer Overflow*** is a condition when an attempt is made to store a value in the integer which is larger than the maximum value it can hold. Like storing a value in `int` type variable in C/C++ that is too big (requires use of `long int` variable type)

> ***Integer Underflow*** is a condition when an attempt is made to store a value in the integer which is smaller than the minimum value it can hold. Like holding a very small value like 1 or 2 in `long long int` variable type in C/C++.

Most compilers seem to ignore these conditions giving unexpected (and wrong) outputs for the given inputs.

### Cause
Both Integer Overflow and Integer Underflow conditions are generally created by heavy or repeated arithmetic operations - such as live statistics.
Also since they cannot be exploited to damage the program, system or any server, there have been no efforts made to try and fix it. The problem being undetectable after it happens and being difficult to spot only makes it worse.

### Importance
It is still considered dangerous since if Integer Overflow occurs at the time of Buffer Length Allocation, it could create a situation where Buffer Length allocated is too small and [[Buffer Overflow\|Buffer Overflow]] occurs later down the line - similar to [[NASDAQ Price Rendering Error\|NASDAQ Price Rendering Error]].

### Avoidance & Solution
Look for loops and repeated mathematical operations on data, check if integer overflow or underflow is enocuntered by making it print out every iteration to find the point where the problem triggers. Use [[Common Debugging Techniques\|Common Debugging Techniques]] and [[Black-Box Testing\|Black-Box Testing]]

---
# Footnotes