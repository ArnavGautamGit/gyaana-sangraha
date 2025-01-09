---
{"dg-publish":true,"permalink":"/File System Structure/","tags":["Academics"]}
---

***Created on: 09/12/2023
Last updated: 09/12/2023***

----
# Index/Contents
[[File System Structure#1. What is a File System?\|#1. What is a File System?]]
[[File System Structure#Footnotes\|#Footnotes]]

-----
# 1. What is a File System?
A Computer deals with files that are generally created by the user.
The File System is a way of managing a large number of files using Folders and Trees.
It uses the concepts of File Attributes, File Operations, File Types and File Structure.
## 1.1 File Attributes
A file is named, for the convenience of its human users, and is referrred in the system using its name. Other Attributes used by the file for easy search:
1. Name
2. Identifier: such as a unique tag/number, name which is non-human readable
3. Type: Source filke, text file, image file etc.
4. Location in the file system
5. Size of the file
6. Time, Date and User ID at creation and last modification
7. Access Control Information or any passwords used to lock the file
## 1.2 File Operations
Operations that the OS need to allow on a file:
1. Create a file
2. Read it
3. Write to it
4. Edit it (Reposition the data in it)
5. Delete it
6. Truncate it (Erase the contents but keep the attributes)
## 1.3 File Types
The OS uses extensions to identify files and if they can be run on the system or not.
Example: Only application (.exe) files cvan be directly executed not source code like C++ (.cpp) or Python (.py)
File Extensions can also be used by individual apps to show which files they made and/or show which type of files are they interested in. Easy example is Microsoft Word which only cares about *.doc* or *.docx* file types. The OS cannot directly read it, but the application can!
## 1.4 File Structure
Files of specific type need to have a specific structure.
Executable files are supposed to have a different structure (containing info about how they need to be loaded in Main Memory and Cache) than *.docx* files Word operates on.
The size of OS becomes cumbersome as the number of file types it can support increases. Hence almost all OS allow other apps to open certain file-types and not give native support (*.docx, .pdf, .xlsx, .epub* etc).

---
# 2. File Access Methods
If there is a file system that manages, stores, displays and allows you to interract with files by allowing you to access them, there must be some Access Methods.
1. Sequencial Access
2. Direct Access
3. Others
## 2.1 Sequencial Access
- Simplest Method
- Information processed in order i.e., line by line.
- Used often in Compilers and Editors.
## 2.2 Direct Access
- File is viewed as a numbered sequence of blocks.
- Each file is made of fixed-length logical records that allow programs to read and write records rapidly in no particular order.
- Used often for Databases.
## 2.3 Other Access Methods
- Custom ones can be built on top of Direct Access.
- Generally involve the creation of Index for the file.
- Index contains pointers to various blocks.
- Indices for larger files may get too large. Best is to create an index for each individual index. Primary index links to secondary index which links to the block useer is looking for.

---
# 3. Directory and Disk Structure
Use the First source in the sources property on the top of this page to read the types of directories:
1. Single-Level
2. Two-Level
3. Tree-Structured
4. Acyclic Graph Structured
5. General Graph Structured

---
Next Chapter ---> [[Secondary Storage Structure\|Secondary Storage Structure]]
# Footnotes


