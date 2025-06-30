---
{"dg-publish":true,"permalink":"/Good Software Engineering Practices/","tags":["Academics","Software-Development"]}
---


---
# Good Software Engineering Practices
> Stuff about Software Development Practices that is beyond the syllabus - stuff that is required to get good at developing software that actually works well & without hiccups.

This includes stuff that you get taught in College and also stuff that software engineers learn with experience.

### Syllabus-based Stuff
> Good Practices that help avoiding problems such as [[Buffer Overflow\|Buffer Overflow]] and [[Stack Overflow\|Stack Overflow]] among others.

Some of these practices include using modern coding languages like [[Python\|Python]] and [[JavaScript\|JavaScript]] instead of C++, C and other such ancient, old, un-updated languages regardless of the speed they offer since on modern machines the difference is negligible. [[Java\|Java]] is an exception to this rule probably. Since languages like [[Java\|Java]], [[C-Sharp\|C-Sharp]] check every array reference to see nothing is out of bounds while Java does not tolerate any stack violations at all.

Another good practice is to keep in mind that special characters like ">" might be needed to be converted to "`&gt;`" to be displayed on Webpages - taking more space in the buffer than the original form. The programmer needs to account for this change and take extra buffer space.

Use `calloc()` instead of `malloc()`
Also prefer `memn`-based functions instead of `str`-based ones.
Use Wrappers and do not foget to use `free()` or similar functions to free up memory space after use.

### Experienced Practices
> I have learnt a few things when I entered the industry and started working on my first job at [[AventIQ\|AventIQ]] and got to solve real issues, build real applications.

Firstly, one must remember that there exists no clean code in the world that is free from all abstractions and is perfectly readable - it does not exist. A good rule of thumb is to check if one would be able to read and remember the context of said code 6 months later. If not, then the code is not made with proper logic that is clear enough.

Secondly, to write better code, one must write code as if it is being reviewed by people on GitHub or if it is being written for being put up on GitHub. That forces the programmer to use more comments, more clear syntax, better formatting.

Thirdly, use Prettier to format the code afterwards. Use Variables with meaningful names which make the purpose of the variable or function clear.

Fourthly, always make the documentation available along with the code - it must be available especially if the code is made with the expectation of being read or used or improved upon by other programmers - in short, it means that docs must be always available in the world of software since employees come and go.

Fifthly, a good programmer who writes "good" software must be able to jump into a codebase in ant mood, figure out which updates to make, make said updates and avoid the urge to rewrite everything throughout the process since the latter is basically a rabbithole that will make the update take much longer since one will be: (a) unfamiliar to the original code and (b) waste the same amount of time in fixing the code again as the amount of time they put in the first time around.

---
# Footnotes