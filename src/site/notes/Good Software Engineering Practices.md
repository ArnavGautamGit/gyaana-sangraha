---
{"dg-publish":true,"permalink":"/Good Software Engineering Practices/","tags":["Academics","Software-Development"]}
---


---
# Good Software Engineering Practices
> Good Practices that help avoiding problems such as [[Buffer Overflow\|Buffer Overflow]] and [[Stack Overflow\|Stack Overflow]] among others.

Some of these practices include using modern coding languages like [[Python\|Python]] and [[JavaScript\|JavaScript]] instead of C++, C and other such ancient, old, un-updated languages regardless of the speed they offer since on modern machines the difference is negligible. [[Java\|Java]] is an exception to this rule probably. Since languages like [[Java\|Java]], [[C#\|C#]] check every array reference to see nothing is out of bounds while Java does not tolerate any stack violations at all.

Another good practice is to keep in mind that special characters like ">" might be needed to be converted to "&gt;" to be displayed on Webpages - taking more space in the buffer than the original form. The programmer needs to account for this change and take extra buffer space.

Use `calloc()` instead of `malloc()`
Also prefer `memn`-based functions instead of `str`-based ones.
Use Wrappers and do not foget to use `free()` or similar functions to free up memory space after use.

---
# Footnotes