---
{"dg-publish":true,"permalink":"/Dangerous C and C++ Functions/","tags":["Academics","Software-Development"]}
---


---
# Dangerous C and C++ Functions
> Functions that must not be used for Programming Projects of any value when the program is written in C and/or C++.

C and C++ are dangerous languages - that a lot of the times to provide speed and low-level control they give too much control to the programmer and expects the programmer to know what to use and what not to use automatically.

### Some Functions to avoid:
1. `strcpy()` - A function used to copy a string. Especially dangerous since it does not take into account that the copied string might be longer than the array length of the destination array & may cause [[Buffer Overflow\|Buffer Overflow]]. 
	1. Use `strncpy()` (with an extra `n` between `str` and `cpy`) for copying any strings.
	2. Another alternative in the form of `strecpy()` exists but one must make sure the space for the destination buffer is $\large4\times$ the source buffer size.
	3. It is visibly obvious, the first option is generally preferred.
2. `cin, gets, scanf()`  - Functions used in C++ and often used in conjunction to input a string. Dangerous since it will input whatever value the user inputs regardless of the maximum length prescribed - assuming the user will somehow know and adhere to it. After picking the input string it then pushes it directly in the buffer or stack, which may cause [[Buffer Overflow\|Buffer Overflow]] or [[Stack Overflow\|Stack Overflow]] - sometimes both.
	1. Better Alternative is the `cin.get` and `cin.getline` functions since they limit input string length by notifying the user that they exceeded length and chop off the extra automatically.
	2. Another alternative for `scanf()` is to use `sscanf()` or `fscanf()`.
	3. If using `cin`, add `cin.width(x);` before the input line `cin >> array;` to bound the `cin` function to input only `x` numbers. Keep in mind that `x` is the buffer length and should be the same as maximum length of array when the array was defined as `char array[x];` else extra size will be wasted.
		1. similarly `snprintf()` is safer than `cout()` but it will override the `.txt` extension if input is more than 60 bytes - which an intelligent attacker can attack.
	4. If using `gets()`, a better alternative is `fgets()` since it measures the maximum size provided and only reads the string until `size-1` and discards the rest - making every string a null-terminated string and makes it very safe.  
3. `strcat()` - Function used primarily for concatenation of two strings into one. It (just like `strcpy()`) has zero regards for the size of the [[Buffer\|Buffer]] being exceeded or not. 
	1. Better use the function: `strncat()` (with an extran `n` between `str` and `cat`) for safe concatenation of strings.
	2. Another alternative of `streadd()` exists if the programmer is willing to put aside $\large4\times$ the source buffer size for the destination buffer.
4. 

---
# Footnotes