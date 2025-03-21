---
{"dg-publish":true,"permalink":"/Computer Registers and Instructions/","tags":["Academics"]}
---


----
# Index/Contents
[[Computer Registers and Instructions#1. Why are Registers needed?\|#1. Why are Registers needed?]]
[[Computer Registers and Instructions#2. What data is stored by which Register?\|#2. What data is stored by which Register?]]
[[Computer Registers and Instructions#Reference Material\|#Reference Material]]

-----
# 1. Why are Registers needed?
We already know what a register is and how it is built using sequential flip-flop circuits last semester, so we will consider that beyond this file.

The Control reads an instructionfrom a specific address in memory and executes it. It then continues by reading the next instruction in sequence and executes it and so on....
This type of instruction sequencing needs a counter to calculate the address of the next instruction after execution of its current one is done. It is also necessary to provide a register in the control unit for storing the instruction code after it is read from Memory.
*Hence, the Computer needs processor registers for manipulating data and a register for holding a memory address*.
## 1.1 Various Types of Registers
1. ***Memory Data Register (MDR or DR)***
2. ***Accumulator (AC)***
3. ***Instruction Register (IR)***
4. ***Temporary Register (TR)***: 
5. ***==Memory Address Register (MAR or AR)==*** : Holds 12 bits, (only addresses are held, not opcode)
6. ***==Program Counter (PC)==*** : Holds 12 bits, (only addresses are held, doesn't hold opcode)
7. ***==Input Register (INPR)==*** : Only hold 8-bit character from input device.
8. ***==Output Register (OUTR)==*** : Only hold 8-bit character from output device.

## 1.2 What data is stored by which Register?
- MDR/DR holds operand read from memory.
- AC is used for general pupose processing.
- IR stores the ***I***nstruction ***R***ead from the memory.
- TR is used to hold temporary data during processing.
- MAR/AR stores width of the memory address.
- PC goes through counting sequence and aid the computer to read sequencial instructions previously stored in memory. Once the execution of the current instruction is done, the address part of a branch instruction is transferred to PC to become address of the next instruction.
# 2. Instruction Code Format
The Memory unit has a compacity of 4096 words and each word contains 16 bits(12 bits for operand address and 4 for operation - 3 bits for opcode and 1 for addressing mode).
If Addressing Mode = 0, then Direct and if Addressing Mode = 1 then indirect.

An Instruction has 3 parts:
1. ***==Address/Instruction Bit==***: Defines if Addressing Mode is Direct or Indirect. Professor uses Address Bit but the book calls it Instruction Bit, I. Defined by a single bit.
2. ==***Operation Code***==: Also called as '*opcode*', used to define operation to be performed. 3 bits are used to define this.
3. ==***Operand's Address***==: The Address where the operand must be. Defined using 12 bits.

| Address-Bit | Opcode (3 bits) | Operand's Address (0th to 11th bits)|
|----|----|----|

If the Opcode is 000, then the operation is Memory Reference.
If the Opcode is 111, we need to check Address-Bit, if 0, then register reference... if 1, then I/O.
## 2.1 How does Input/Output work?
Two Registers are used to input and output. The Input Register (INPR) receives an 8-bit character from an input device. The Output Register (OUTR) holds an 8-bit character for an output device.
INPR receives a 8-bit character which gets transferred to AC. OUTR takes the 8-bit character and send it to an output device. Hence, character by character the entire output is printed.
# 3. All about the 'Common Bus System'
The basic computer has eight registers, a memory unit, and a control unit. Paths must be provided to tranfer information from one register to another and between memory and registers. The number of wires will be excessive if connections are made manually.

Check Figure 5.4 in the Reference Book, Page 132 as you read the following sub-headings.
## 3.1 How is the Common Bus System Connected?
The Outputs of seven registers and memory are connected to the common bus. The specific output that is selected for the bus lines at any given time is determined from the binary value of selection variables S2, S1 and S0. The Number along each output value of the required binary selection. The Memory receives the contents of the bus when its write input is activated.
## 3.2 How is data sent and received?
When the contents of MAR and PC are applied to the 16-bit common bus, the four most significant bits are set to 0000. When MAR or PC receive information from the bus, only the 12 least-significant digits are copied to the register. INPR is connected to provide info through the bus, OTR takes infro from the bus and delivers it to an output device. No transfer from OUTR to any other register.

---
Next Chapter in COA ---> [[Intel 8085 Microprocessor\|Intel 8085 Microprocessor]]
# Reference Material
1. "Computer Systems Architecture" Book written by M. Morris Mano (Section 4.22, Book 2029 in J128 LRC)

