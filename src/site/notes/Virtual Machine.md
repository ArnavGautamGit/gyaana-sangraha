---
{"dg-publish":true,"permalink":"/Virtual Machine/","tags":["CompSci","COA"]}
---


----
# Index/Contents
[[Virtual Machine#What is a Virtual Machine?\|#What is a Virtual Machine?]]
[[Virtual Machine#How does a Virtual Machine Work?\|#How does a Virtual Machine Work?]]
[[Virtual Machine#What are the Most Popular VMs in the World?\|#What are the Most Popular VMs in the World?]]
[[Virtual Machine#Reference Material\|#Reference Material]]

-----
# What is a Virtual Machine?
The Fundamental Idea of a Virtual Machine is to use the hardware of a single computer (CPU, RAM ROM, Storage, Bus, Network Cards etc.) to power different environments giving the illusion that each environment is running its own PC.
Since this is a ILLUSION of having a VIRTUAL PC inside your main MACHINE... the illusionary runtime envioronment is called a Virtual Machine.
# How does a Virtual Machine Work?
A Virtual Machine requires a Virtual Machine software which allows the VM to be hosted. It is like an app with its own UI. Examples: VirtualBox or VMware Workstation.
These Softwares run in Kernel Mode.
The VMs running inside them run in User Mode (otherwise how will you access their OS lol)
For the VM to work properly, we must also have
- A Virtual User Mode
- A Virtual Kernel Mode
- A Mini-Disk (Isolated area of your base hardware Storage Assigned to the VM for storing data inside it.)
The Main User and Kernel Mode of the OS of your PC is running the VM and VM Software respectively, but the VM (and its own OS) will also need to have their own Virtual Kernel and User Modes to work properly and ACTUALLY execute the Processes. 

---
Next Chapter in COA ---> [[Evolution of Multi-Level Machines\|Evolution of Multi-Level Machines]]
## Reference Material
Class Notes and PPT

