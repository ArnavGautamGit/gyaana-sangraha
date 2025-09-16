---
{"dg-publish":true,"permalink":"/Independent Courses/IIT Kanpur CyberSec/Windows Powershell/","tags":["Academics"]}
---


---
# Windows Powershell
> An [[OS Shell\|OS Shell]] designed for [[Microsoft Windows\|Microsoft Windows]] [[Operating System\|Operating System]] based on concepts of [[Object Oriented Programming\|Object Oriented Programming]].

In Windows Powershell, the commands are called "cmdlets" (pronounced "command-lets") with the same concept of a small pig being called a piglet.

### Commands (Cmdlets)
The Commands are structured quite close Natural Language in a "verb-noun" fomrat and behave differently than any Terminal present in [[Linux\|Linux]] distributions based on [[Debian Linux\|Debian Linux]].
For example: `get-childitem` in place of `ls` or the command `get-verb` to figure out all the verbs that one can use.

Commands can be used to search among all commands.
For example: `get-command verb-*` tells Windows to fetch all commands that use that particular verb with other nouns (the term "verb" in the example is a placeholder).

On the flip side, if you only know the noun and are struggling with finding the verb to complete the command then there is the same command structure with the asterisk replacing the verb instead. 
For Example: `get-command *-noun` tells Windows to fetch all commands that use that particular noun with other verbs (the term "noun" in the example is a placeholder).

If you do not understand what a particular command does then use: `get-help <command>` and Powershell will explain it to you. If you want to understand how to execute a particular set of instructions and pass them as a script (via [[Independent Courses/IIT Kanpur CyberSec/Windows Powershell ISE\|Windows Powershell ISE]]) you can leverage AI.

### Object-Oriented Shell
All outputs for Powershell commands are Objects i.e., one can iterate on them with multiple commands and even perform Command Chaining. Each Output/Object has its own set of Properties (attributes) and Functions (methods).

Example: if one uses the `get-date` command on Powershell, we can leverage its built-in functions like `(get-date).year` to get the year specifically. Similarly there are many functions for each property of any output. This is not available on [[Independent Courses/IIT Kanpur CyberSec/Command Prompt (CMD)\|Command Prompt (CMD)]].

### Command Chaining
Using various characters like a Pipe (i.e., | ) to chain commands whose output will be used as an input for the next command, it is also called Command Piping due to the use of Pipe character. Command Chaining is present in almost every big and popular [[OS Shell\|OS Shell]] on the planet.

Adding a hyphen allows us to add auxiliary commands like `-lines` which output the number of lines of the output object which can be useful in certain situations.


---
# Footnotes