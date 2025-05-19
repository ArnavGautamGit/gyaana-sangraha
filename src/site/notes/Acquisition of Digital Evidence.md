---
{"dg-publish":true,"permalink":"/Acquisition of Digital Evidence/","tags":["Academics","CyberSec"]}
---


---
# Acquisition of Digital Evidence
> One of the first steps in [[Digital Forensic Analysis\|Digital Forensic Analysis]] which starts with the total seizure of all [[Digital Evidences\|Digital Evidences]] available from the crime scene.

Although this note focuses on Acquisition Techniques for Evidence Acquisition, but we also need to lightly touch on the planning before hand.

### Pre-Acquisition Phase
Some things we have to do before we directly jump in to search the suspect's devices and the services they log on to for [[Digital Evidences\|Digital Evidences]].

These Pre-Requisites include: (1) Obtaining Legal Clearances like latest applicable warrants and (2) Preparation like devices & equipment the Forensic Team would themselves need since there may be a need to bring your Macbook if the suspect has one. 

### Types Acquisition Techniques
- ***==Live Acquisition==***: Used often for Volatile Data Storage such as RAMs ([[Acquisition of Digital Evidence#^1\|#^1]]).
- ***==Dead Acquisition==***: Used for Non-Volatile Data Storage such as SSDs/HDDs.
- ***==Mobile Device based Acquisition==***: Used for gathering data off of phones using [[Logical Data Extraction\|Logical]] or [[Physical Data Extraction\|Physical Data Extraction]] i.e., file system access or bit-by-bit extraction.

The First Two require [[Forensic Imaging\|Forensic Imaging]] Tool called "[[FTK Imager\|FTK Imager]]".

### Acquisition Techniques for Windows
Missed that class (was at Somnath)

### Acquisition Techniques for Mac
[[Target-Disc Mode (TDM)\|Target-Disc Mode (TDM)]] is one of the popular techniques to collect [[Digital Evidences\|Digital Evidences]] from an otherwise very secure Mac. The feature originally was meant for Data Recovery from broken or damaged Macs but can also be used to copy data (here, evidence) off a perfectly fine Mac.

### Acquisition Techniques for iPhones & iPads
In iOS or iPadOS, one just needs to connect the iPhone or iPad to their Macbook being used for Forensic Analysis & click "Trust this device" on the unlocked iPhone once the password is extracted out of the suspect via interrogation & then download the entire phone's storage to a Hard disk...

Then the process is the same as described in [[Target-Disc Mode (TDM)#Verifying the Target Disk\|Analysis & Verification of Disks in TDM]] since we have essentially copied the entire disk.

### Acquisition Techniques for Android Phones
 Following Text is transcluded from the main note: [[Mobile Device Forensics\|Mobile Device Forensics]]


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/mobile-device-forensics/#forensic-tools-required" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



### Forensic Tools Required
Tools such as [[Magnet AXIOM\|Magnet AXIOM]], [[Cellebrite (UFED)\|Cellebrite (UFED)]] or [[Oxygen Forensic Detective\|Oxygen Forensic Detective]] are used by Law Enforcement and Forensic teams for [[Logical Data Extraction\|Logical]] and [[Physical Data Extraction\|Physical Data Extraction]]. In these methods the Collection of Data is performed by scanning and copying the entire File System of the device along with any files that are contained inside it.

If the device has a locked or encrypted disk, then the option of Physical Data Extraction exists where the entire disk is copied bit-by-bit & reconstructed - which bypasses most encryptions.


</div></div>



---
# Footnotes
1. Live Acquisition refers to the performing the entire [[Digital Forensic Analysis\|Digital Forensic Analysis]] before the PC or laptop or network or any other source device/service of Digital Evidence is shut off or logged out of. Since these services or device hardware may wipe data if allowed to be shut off or logged out of.
{ #1}

2. 