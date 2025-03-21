---
{"dg-publish":true,"permalink":"/Basics of Computer Architecture/","tags":["Academics","COA"]}
---

---
# Index/Contents
[[Basics of Computer Architecture#What is the structure of a Computer?\|#What is the structure of a Computer?]]
[[Basics of Computer Architecture#What does a Control Unit do?\|#What does a Control Unit do?]]
[[Basics of Computer Architecture#What does an ALU do?\|#What does an ALU do?]]
[[Basics of Computer Architecture#Compiler vs Translator vs Interpreter\|#Compiler vs Translator vs Interpreter]]
[[Basics of Computer Architecture#Reference Material\|#Reference Material]]

-----
# What is the structure of a Computer?
A Computer is Structured in multiple levels and multiple ways. We'll see as many as possible in this notes file here.
It is done mainly on 3 levels:
1. The Physical Level of the PC
2. Structure of the CPU
3. Structure at the level of Individual Control Units
## Physical Level of a PC
1. CPU 
2. Main Memory (Cache, RAM, ROM)
3. Secondary Memory (SSD, HDD etc.)
4. Input and Output Devices (Mouse, Monitor, Keyboard etc.)
5. Tertiary Memory (or External Secondary Memory like Pendrive etc.)
## Inside CPU of the PC
1. ***Registers***: Sequencial Circuit in Digital Sysytems made using Flip-Flops.
2. ***ALU***: Arithmetic Logic Unit, It is responsible for performing *arithmetic*, *logical* and *shift* operations. It also saves data with connection to Memory.
3. ***Internal Bus***: used to connect CPU components to Memory and transport Data between the two. There is also a System Bus which connects RAM, ROM with CPU and possibly other components too. The Bus is controlled by Control Unit itself.
4. ***Control Unit***: It is responsible for managing and coordinating the execution of instructions and controlling the flow of data within the CPU and between the CPU and other parts of the computer system.

---
# What does a Control Unit do?
The Control Unit performs the following key functions:
1. ==***Instruction Fetch***==: It fetches instructions from the memory, decodes them, and determines the type of operation to be performed.
2. ==***Instruction Decoding***==: The Control Unit interprets the fetched instructions and determines the sequence of microoperations required to execute the instruction.
3. ==***Instruction Execution Control***==: It controls the execution of instructions by issuing control signals to other CPU components, such as the Arithmetic Logic Unit (ALU), registers, and memory.
4. ==***Data Flow Control***==: The Control Unit manages the flow of data between different components of the CPU, such as registers, ALU, and memory.
5. ==***Timing and Synchronization***==: It generates timing signals to coordinate the activities of different CPU components, ensuring that instructions are executed in the correct sequence and at the appropriate time.
6. ==***Exception Handling***==: The Control Unit detects and handles exceptional conditions, such as invalid instructions, arithmetic overflow, or division by zero, by generating appropriate interrupt signals.

---
# What does an ALU do?
The ALU is connected to the CPU's control unit, which sends it instructions to execute specific operations on data stored in the CPU's registers. It is also connected to the memory, which stores the data that the ALU operates on. ==***Essentially, the ALU is the part of the CPU that performs the calculations necessary for the computer to function.***==

---
# Compiler vs Translator vs Interpreter
In Programming, C uses a Compiler... Python uses an interpreter. Some Languages need a combination of a Translator and Compiler (called Transpiler).
Hence people have started to use theses terms interchangebly. What is the difference though? More importantly, is there a difference?

| Areas          | Compiler                                   | Translator                                 | Interpreter                              |
| -------------- | ------------------------------------------ | ------------------------------------------ | ---------------------------------------- |
| Input          | source code of a low-level language        | Source code in one language                | Source code in one language              |
| Output         | Machine code or executable file            | Translated source code in another language | Result of executing source code directly |
| Execution      | Separate compilation and execution stages  | Immediate translation and execution        | Direct interpretation and execution      |
| Performance    | Generally produces faster-running programs | Varies based on translation approach       | Generally slower compared to compilers   |
| Portability    | Produces platform-specific executables     | May produce platform-specific code         | Code can be executed on any platform     |
| Error Handling | Provides comprehensive error messages      | May provide error messages                 | Stops execution on the first error       |
| Dependency     | Relies on the presence of a compiler       | No dependency on a separate tool           | No dependency on a separate tool         |
| Examples       | GCC (GNU Compiler Collection)              | Babel (JavaScript transpiler)              | Python interpreter                       |

It's worth noting that the terms "translator" and "interpreter" can sometimes be used interchangeably, and the line between them can be blurry in certain contexts since modern programming has been using the best of both by merging the two.

*==Compiler==, although ==produces the fastest running programs, it produces only platform-specific code.==* Your compiled code may only run on Windows. 
*==Interpreters and Translators may be slow but they are more flexible. Interpreters are the most flexible and translators are comparitively faster.==* 
{especially using the Ahead-of-Time (AOT) Technique or the Just-in-Time (JIT) technique used by Java, .NET and JavaScript.}
{ #compilers}


*Nowadays*, for the reasons stated above, Languages and Frameworks that use a combination of Translators and Interpreters are more common since they are a perfect blend between Performance and Flexibility.
Example: Python is more widely used than C++ in the U.S.

---
Next Chapter ---> [[Virtual Machine\|Virtual Machine]]
# Reference Material
Slides of Module 1 available on Google Classroom.
