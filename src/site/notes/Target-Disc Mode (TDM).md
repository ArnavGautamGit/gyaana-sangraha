---
{"dg-publish":true,"permalink":"/Target-Disc Mode (TDM)/","tags":["Academics","CyberSec"]}
---


---
# Target-Disc Mode (TDM)
> A feature provided by Apple in their Mac Desktops and Macbook Laptops which allows mirroring the drive of 1 Mac Machine on another for Data Recovery in case a Mac's parts or Motherboard are damaged & the stored files need to be copied onto a new Mac.

This "feature" is often reverse-engineered as a [[Digital Forensic Analysis\|Digital Forensic Analysis]] Technique  by Law Enforcement Agencies for [[Acquisition of Digital Evidence#Acquisition Techniques for Mac\|Acquisition of Digital Evidence from an Apple (Mac) Machine]].

### Pre-Requisites
1. Two Mac Devices: One Host and One Target
2. Thunderbolt or Firewire Port
3. Forensic Software: Tools like [[FTK Imager\|FTK Imager]], [[EnCase\|EnCase]] and dd.
4. Writer-Blocker: Prevents Accidental Modification on Target Disk.

---
# Acquisition Procedure
The Procedure for [[Acquisition of Digital Evidence\|Acquisition of Digital Evidence]] has the following steps:
1. Preparation of Evidence Mac
2. Connecting Evidence Mac with Forensic Workstation (Law Enforcement's Mac)
3. Verifying Target Disk
4. Documenting the process

### Preparing the Evidence Mac
1. Shutdown the Mac
2. Enter Target Disk Mode 
	1. Press & Hold `T` key on Keyboard while powering on the Mac.
	2. Keep the key held until a Thunderbolt, Firewire or USB is visible on the screen.

### Connecting the Evidence Mac to Forensic Workstation
1. The Forensic Workstation must also be a Mac (the one used by Law Enforcement)
2. Use Thunderbolt/Firewire Cable to connect the Evidence Mac with Workstation
3. Verify the connection by checking the target disk of the Evidence Mac is visible as external disk on forensic workstation.

### Verifying the Target Disk
1. Use Forensic Tools
	1. [[FTK Imager\|FTK Imager]]: Generate Forensic Image
	2. dd: used to collect multiple images or files ([[Target-Disc Mode (TDM)#^1\|#^1]])
	3. [[EnCase\|EnCase]]: For more detailed [[Digital Forensic Analysis\|Digital Forensic Analysis]]

### Documenting the Process
1. Record all the steps
2. Compare the Hash Values of Data on original Evidence Mac and the Hash Value of Data on the Forensic Mac to confirm Data [[Integrity\|Integrity]] and that no data is changed in the transfer process. 


---
# Footnotes
1. dd is a command line tool which can collate multiple [[Forensic Imaging\|Forensic Images]] & Files in one go.
{ #1}

	1. It uses the command `sudo dd if=/dev/diskx of=/path/to/img Lmg bs=4m`
	2. Replace the `diskx` with proper disk identifier of the actual disk.