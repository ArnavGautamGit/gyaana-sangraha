---
{"dg-publish":true,"permalink":"/Intel 8085 Microprocessor/","tags":["COA","Academics"]}
---


----
# Index/Contents
[[Intel 8085 Microprocessor#1. What was the Intel 8085 Microprocessor?\|#1. What was the Intel 8085 Microprocessor?]]
[[Intel 8085 Microprocessor#2. Instruction Set and Programming for Intel 8085\|#2. Instruction Set and Programming for Intel 8085]]
[[Intel 8085 Microprocessor#Footnotes\|#Footnotes]]

-----
# 1. What was the Intel 8085 Microprocessor?
It was the successor of the 8080 Microprocessor (also made by Intel) and had some features added on top. It was fully backwards cpmpatible on the software bit except the RIM and SIM pins because they did not exist on the 8080 at all.
The Intel 8085 Microprocessor was launched in 1976 and discontinued in 2000.
It was already eclipsed by the Intel 8086 that launched two years later in 1978 but it was discontinued earlier in 1998.
## 1.1 Registers and Hardware
The 8085 was a 8-bit registr with 16 address lines.
There was
- An 8-bit Accumulator (abbreviated to ACC, AC or A)
- There 6 more 8-bit registers named from B, C, D, E, H and L
- 16-bit Stack Pointer (SP)
- 16-bit Program Counter (PC)
- 16-bit Program Status Word (PSW)

The 8085 had (as previously mentioned) 16 address lines and 8 data lines. Which allowed for register pairing for the 8-bit registers... 2 registers could combine together to proces 16 bit instructions as well...
The Registers pairs allowed are: BC, DE and HL
The stack pointer was used to maintain stack in the memory. It points to the top of the stack at all times.
The PSW register has the higher order 8-bits contain register contents and lower order 8-bits contain 5 condition flags:
- ***ZERO (Z)***: Used if result is zero
- ***SIGN (S)***: Used if result is negative
- ***PARITY (P)***: Used for Even Parity (number of 1s in binary is even)
- ***CARRY (CY)***: USed if there is a carry after 7th (MSB) bit.
- ***AUX. CARRY (AC)***: Used if carry from third to fourth bit 
(Note: X = undefined)

The 8085 had 8 data lines which were multiplexed with lower addres lines. Thus $\large AD_0$ to $\large AD_7$ and $\large A_8$ to $\large A_{15}$ form the 16 address lines of the address bus and the $\large AD_0$ to $\large AD_7$ are bi-directional data lines. They are capable of ging High impedance state when needed (making them tristate).
## 1.2 Memory Interfacing
1. 8085 has 16 address lines, upto 64 KB (kilobytes) memory space may be interfaced. A number of memory chips both ROM and RAM can be connected within this space.
2. The 8085 will have to issue Read-Write Control signals to memory to carry out thesse operations.
3. Since the lower-order address lines $AD_0$ to $\large AD_7$ are used for data as well, in time-multiplexed function, there is a necessity to have a signal that informs us as to whether these address lines contain data or address.
4. Since a number of memory chipscan be connected and the use of memory space can be planned based on the application, there would be the necessity of generating a chip-select signal for the memory chip where the Read/Write operation is to be performed.
## 1.3 Pin Diagram for the 8085
The 8085 was made with 40 pins numbered in a U-shape.
We first see the pin diagram and then discuss individual pins and what they do.
![8085 Pin Diagram.jpg](/img/user/Vaulted%20Images/8085%20Pin%20Diagram.jpg)
![8085 Pin Meaning 1-2.jpg](/img/user/Vaulted%20Images/8085%20Pin%20Meaning%201-2.jpg)
![8085 Pin Meaning 2-2.jpg](/img/user/Vaulted%20Images/8085%20Pin%20Meaning%202-2.jpg)

### 1.3.1 Interrupt Pins - TRAP, RSTs, INTR, INTA
The TRAP is both (positive) edge and level-triggered$\large ^{[1]}$, non-maskable$\large ^{[2]}$ interrupt which cannot be disabled and has been reserved for power failure and/or other fatal interrupts.
The INTR is a general-purpose, level-triggered interrupt which is available on the 8080 as well.
The INTA is the pin which acknowledges the INTR interrupt.
RST 7.5 is the only RST pin which is edge-triggered while 6.5 and 5.5 are both level-triggered.

NOTE: All Pins except TRAP are maskable.
### 1.3.2 Serial Inputs and Outputs - SID and SOD
Serial Input and Output is facilitated by 2 lines: SID and SOD.
SID means Serial Input Data.
SOD means Serial Output Data.
SID was used by other serial output devices that were connnected to the 8085 to serve it data.
SOD was used by other serial input devices that were connected to the 8085 to take data from it.
***The Read Interrupt Mask (RIM)*** instruction transfers the bit information present on the SID line to the 7th bit on the AC register. ***The Set Interrupt Mask (SIM)*** instruction transfers the 7th bit of AC register to the SOD line.
# 2. Instruction Set and Programming for Intel 8085
The Intel 8085 has its unique ISA and we are supposed to learn it in this course (even though this "technology" has been extinct sinc 2000 - 23 years ago)
## 2.1 Program Status Word - PSW
The PSW is a 16-bit register. The higher order 8 bits contain AC register's info, lower 8 have 5 condition flags.
The PSW may be pushed to stack to save the ACC and flags status during interrupt execution and subroutine execution.
The PUSH and POP instructions are used for storing and retrieving the PSW contents from the stack.
This is what a PSW looks like conceptually:

| Accumulator Register Contents | S | Z | X | AuxC | X | P | X | CY |
|---|---|---|---|---|---|---|-|-|
15                                                    8     7    6    5           4     3    2    1       0
## 2.2 Operand Types
The 8085 can only use 8-bit data for calculations naturally... you have to split the data into higher and lower order data (8-and-8 split) to use 16-bit data and calculate each half separately.
## 2.3 Addressing Modes
![8085 Addressing Modes 1.png](/img/user/Vaulted%20Images/8085%20Addressing%20Modes%201.png)
![8085 Addressing Modes 2.png](/img/user/Vaulted%20Images/8085%20Addressing%20Modes%202.png)
Check list of instructions like MVI, MOV, LDA et cetera from the Reference Book

---
Next Chapter ---> [[Cache Memory\|Cache Memory]]
# Footnotes
"Microprocessors and Microcontrollers" by Krishna Kant, Book 4887 in J128 LRC has been used as a source for this note. It can be found in Rack Number 4.22 in the extreme left shelf in the top floor of the LRC.
$\large^{[1]}$ ***Level-triggered Interrupt***: A high signal should be present on the lines when the interrupt is recognised. ***Edge-Triggered Interrupt*** is recognised when the interrupt signal is going from low to high (positive) or  when going from high to low (negative); not when it is consistent at a level. 
$\large^{[2]}$ ***Masking*** an interrupt means to hide it from the processor. The interrupt came in and was shoved under the rug.

