---
{"dg-publish":true,"permalink":"/Evaluating Performance of Computer Systems/","tags":["Academics","COA"]}
---


----
# Index/Contents
[[Evaluating Performance of Computer Systems#What is Performance in a Computer System?\|#What is Performance in a Computer System?]]
[[Evaluating Performance of Computer Systems#What does Performance depend on?\|#What does Performance depend on?]]
[[Evaluating Performance of Computer Systems#What all has gotten better in the Computing world?\|#What all has gotten better in the Computing world?]]
[[Evaluating Performance of Computer Systems#How does Performance depend upon the ISA?\|#How does Performance depend upon the ISA?]]
[[Evaluating Performance of Computer Systems#How does Computer Organisation impact Performance?\|#How does Computer Organisation impact Performance?]]
[[Evaluating Performance of Computer Systems#How can Computer Performance be compared?\|#How can Computer Performance be compared?]]
[[Evaluating Performance of Computer Systems#How do you calculate Speedup in Performance?\|#How do you calculate Speedup in Performance?]]
[[Evaluating Performance of Computer Systems#Reference Material\|#Reference Material]]

-----
# What is Performance in a Computer System?
*==Performance is the amount of useful work accomplished by a Computer System.==*
***Performance Comparisons are drawn by comparing the amount of useful work a computer can perform in a single unit of time with another. The one that can do it faster is considered better***.

Sometimes these results are quantified (like Antutu scores for Android Phones).
How this Quantification is done and if it is useful is beyond the scope of the syllabus.

We first discuss... how is Performance impacted, how it is measured, the formulae related to the said measurement etc.
# What does Performance depend on?
Performance is based on Efficiency.
Efficiency of what?
- Efficiency of the Technology used to build the PC and its parts (motherboard, RAM, CPU etc.)
- Efficiency of the Instruction Set Architecture of the Computer (nowadays it is standardised almost)
- Efficiency of the CO (Computer Organization)
- Efficiency of the Software involved (like the OS - some OS like Linux is more efficient than Windows)
# What all has gotten better in the Computing world?
Better or Worse is subjective, plus... you can say better and worse only if you know what you are comparing from. Let's say we are striking a comparison between 1945 and 2020...
The Difference is huge in multiple domains...

|Domains|1945|2020|
|-|-|-|
|Technology|ENIAC was the best computer of the time which weighes 27,200kgs (took an entire room to fit) and had a performance of 300 flops/s| A laptop from today is 1.5kgs (fits in a backpack) and has 3 Gigaflops/s of performcance|
|Cost|ENIAC costed 4.6 Million USD|A normal Laptop from today costs 1000 USD on average but ENIAC can be destroyed by a $30 smartwatch in terms of computational power|
|Memory|ENIAC had the Memory of 200 bytes| A Modern Laptop for $1000 offers 1TB memory with separate 500GB SSD to store your OS which totals to 1.5TB|
|Power|ENIAC took 20,000 Watts to power it up| A modern laptop takes just 5.5 watt, although big power intensive PCs can have Power Supplies as big as 550W but systems like that are not purchasable under $1000|

# How does Performance depend upon the ISA?
Instruction Set Architecture, or ISA, for short - is largely standardised but it has one problem. There exists TWO Standards upon which the ISA is built.
These two standards are CISC and RISC which define code density.
Code Density and Number of Operands define how good the ISA is going to be.
Example: Stack Machines have 0-operands, Register Machines have 2-operand or 3-operand ISA.
A Laptop is obviously equipped with many more operands.
It all burns down to CISC and RISC since the number of operands will be same across all laptops (Since all laptops have the same mathematical ability)

|CISC|RISC|
|-|-|
|Gives more importance to Hardware|Gives more importance to Software|
|Instruction with multiple sizes and formats|Same size and formatted instructions|
|Uses less registers|Uses More Registers|
|More addressing modes|Few addressing modes|
|Complex Microprograms|Complex Compilers|
|Instructions can take varying cycle time|Instructions take 1 cycle time|
|Pipelining is hard| Pipelining is easy|

CISC is more economical in saving the money spent on each register but it is harder to program and use. RISC is more standardised and in this era where registers are getting very cheap, it seems that the RISCs are taking the lead.
# How does Computer Organisation impact Performance?
A system being Multi-core or Single-core (one core means one Processor).
Each Core has its own registers and its own L1 cache (plus the entire unit has a combined L2 cache)
![Memory Hierarchy.png](/img/user/Vaulted%20Images/Memory%20Hierarchy.png)
# How can Computer Performance be compared?
Easiest way to compare Computer Performance is by comapring the Execution Time (the time taken by the the Computer to finish the given task)
Now, all that is left is to understand how to calculate Execution Time.

$$ Execution Time = A \times ClockTime $$
$$ClockTime = \frac{1}{ClockRate} $$
$$ A = IC \times CPI $$
here,
A = CPU Clock Cycles for a singular program
Clock Time = Clock Cycle Time
CPI = Average Clock Cycle Per Instruction
IC = Instruction Count

Using this,
$$\LARGE Execution Time = IC \times CPI \times ClockTime $$
OR (in terms of Clock Rate)
$$\LARGE Execution Time = \frac{IC \times CPI}{ClockRate}$$
Note, Performance (P) is the inverse of Execution Time.
$$Performance = \frac{1}{ExecutionTime}$$
Performance Ratio is the ratio between the performance of two tasks. (No need to mention a formula) and it is generally denoted by n.
$$\large n = \dfrac{P_a}{P_b}$$
MIPS rate is Million Instructions per seconds
$$\LARGE MIPS = \dfrac{IC}{ET \times 10^6}$$
# How do you calculate Speedup in Performance?
Calculating Speedup is easy, it is a Performance Ratio of Old Performance to New Performance.
(Note ET is the short-form for Execution Time)
$$Speedup = \frac{P_{old}}{P_{new}} = \frac{ ET_{new}}{ ET_{old}}$$

**==We can also use *Amdahl's Law*:==** (Note: the formula remains same with or without the summation symbol. The said sum symbol is used only when multiple programs have been given)
$$\LARGE Speedup = \frac{1}{(1-\sum{F})+\sum\frac{F}{S}}$$
where, 
F = fraction enhanced or fraction sped-up
S = factor of enhancement
(1-F) = fraction un-enhanced or fraction unaffected.

==**We can also use *Little's Law*:**== It says that in the long-term, steady state of a production system, the average number of items L in the system is the product of the average arrival rate $\lambda$ and the average time W that an item spends in the system, that is, $$\LARGE L = \lambda W$$
Here, $W =$ Turn Around Time for an individual item

---
Next Chapter ---> [[Computer Registers and Instructions\|Computer Registers and Instructions]]
# Reference Material
Class Notes and PPT only.

