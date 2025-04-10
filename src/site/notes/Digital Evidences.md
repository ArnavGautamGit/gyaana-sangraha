---
{"dg-publish":true,"permalink":"/Digital Evidences/","tags":["Academics","CyberSec"]}
---


---
# Digital Evidences
> Items and Data such as system logs, call logs, timestamped messages, social media activity or other data or meta data that can act as evidence to prove a [[Cyber Crime\|Cyber Crime]] or [[Malicious Hacking\|Malicious Hacking]] case in court.

Evidences and their forms may change depending on the Operating System used by the user. Linux Filesystem is ext4 whereas NTFS is primarily used by Windows while Mac uses HFS+. FAT32 is also used by Windows but generally considered cross-platform.

### Identification
The Forensic Team must be able to identify all of the evidence pertaining to a case & be able to store & collect it. Popular points of Evidence include: 
A) [[Computer Artefacts\|Computer Artefacts]]
B) [[Browser Artefacts\|Browser Artefacts]]
C) Call Logs
D) Social Media Activity
E) Computer Logs and Network Logs
F) GPS Logs (Google Maps Digest) 
G) AI Chat Logs
H) Any messages hidden inside Images using [[Steganography\|Steganography]]
among other relavant material depending upon case details.

### Collection
Evidence is often collected in the form of files copied from the filesystem or as [[Computer Artefacts\|Computer Artefacts]] and [[Browser Artefacts\|Browser Artefacts]] of various operating systems and browsers used on the Machine. 
It is important to note that Digital Evidences collected in this phase are copied onto Tamper-Proof SSDs & not older commercial ones. Original Drives may be used for Forensic Research but they are mainly used to tally data to showcase that no evidence tampering has occured. 

If Data from the Evidence Drives was wiped in the [[Security Incidents\|Intrusion]] that we are investigating, then the [[USB History\|USB History]] can be checked and analysed.

### Preservation
The Drives storing the evidence are then put through [[Whole Disk Encryption\|Whole Disk Encryption]].
They must also be then properly labelled by drive identifier and device identifier. Certain companies may use individual names or numbers as identifiers for devices and each OS assigns a name to individual Storage Drives connected to it.

Regardless of if the same drives from the source are being used or data being copied onto new drives, they must also be placed in auto-seal ziplocks which are labelled by devices and carry the same drives that the specific computer/laptop was having in it.

We must also maintain and store any Hash Values of the Storage Devices to check and recheck if there have been any unauthorised changes that have been made in the drives. This protects the Data [[Integrity\|Integrity]] of the individual drives and in-turn protects the Integrity of the Evidence. 

Use Industry Standard Practices as described in NIST, ISO 27037.

### Documentation & Analysis
Documentation of the Evidence is the most important step. Documentation helps identify the chain of custody from the Evidence first being generated and being collected by the Forensic Team, all the way to the Court Presentation. 

All the processes performed on the Evidence for Analysis are also documented to help in making the results more reproducible by other experts.

Documentation is also immensely helpful in case the Hon'ble Court asks to transfer the case to another authority or in cases where the Forensic Team experiences changes in personnel.

---
## Classification of Digital Evidences
Digital Evidences are classified on the basis of Data Volatility and other factors. The Classification is given below.



---
# Footnotes