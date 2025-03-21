---
{"dg-publish":true,"permalink":"/Secondary Storage Structure/","tags":["CompSci"]}
---


----
# Index/Contents
[[Secondary Storage Structure#1. What is Secondary Storage?\|#1. What is Secondary Storage?]]
[[Secondary Storage Structure#2. Overview of some Mass Storage Structures\|#2. Overview of some Mass Storage Structures]]
[[Secondary Storage Structure#3. List of Disk Scheduling Algorithms\|#3. List of Disk Scheduling Algorithms]]
[[Secondary Storage Structure#Footnotes\|#Footnotes]]

-----
# 1. What is Secondary Storage?
Secondary Storage is the disk (or a partition of it) which stores data for long term use in Computers. The Primary Storage being Memory (RAM and ROM).
In certain OS like Windows, there is a (C:) Drive and a (D:) where the latter is called the secondary storage since the OS and its OS specific files run in the former. That definition is still consistent with ours. This partition is done due to the OS being too heavy to be run on the same drive as data storage.
Also note that throughout these notes, Secondary Storage and Mass Storage are used interchangably.
# 2. Overview of some Mass Storage Structures
## 2.1 Magnetic Disks
Each disk has the platter (the actual disk that spins) shaped like a mini CD at the diameter from 1.8 to 5.25 inches. Both surfaces of the platter are covered with a magnetic material. We storre information on the disk magnetically when the disk is made to spin on the (sometimes motorised) spindle.
For HDDs, the size of the disk ranges from 1.8 to 3.5 inches in diameter. Much smaller disk with many more tracks and sectors - hence more storage in smaller size.
### 2.1.1 How is Data stored and retreived from a Magentic Disk?
The platter spins on a spindle, with read/write arms on both surfaces of the platter(s).
The platter spins to position the correct track and sector([[Secondary Storage Structure#^1\|#^1]]) under the read/write head for the read/write operation to be performed. Screenshopt taken from a newer 2018 edition (unlike the 2010 edition available in the college)
![Magnetic Disk Diagram.png](/img/user/Vaulted%20Images/Magnetic%20Disk%20Diagram.png)
Note that, the arm is retractable and extendable, the cylinder is an imaginary representation. The radius of the cylinder corresponds to the radius of the track. The read/write head switchin cyllinders means it is switching positions to a different track at a different radius from the spinning spindle.
### 2.1.2 What is Disk Speed? What are its components?
When the disk is in use, it can spin anywhere between 60-200 times per second 
(5,400 - 15,000 RPM). 

The Disk Speed has two parts: ***==Transfer Rate==*** and ***==Positioning Time==*** which refer to the time taken for data transfer and disk positioning respectively. The latter (Positioning Time) is sometimes also called ***Random-Access Time***.
### 2.1.3 What is a Head Crash?
Although the disk platters are coated with a thin protective layer, ==***the head will sometimes damage the magnetic surface. This accident is called a head crash. A head crash normally cannot be repaired***==; the entire disk must be replaced, and the data on the disk are lost unless they were backed up to other storage or RAID protected.
### 2.1.4 What is the Disk Structure like?
There are two types of Disk Structure: ***Constant ANGULAR Velocity (CAV)*** and ***Constant LINEAR Velocity (CLV).*** (Source: [[Secondary Storage Structure#^2\|#^2]])
CAV is used in HDDs while CLV is used in CD-ROMs and DVDs.
In a CAV, the disk spins at consistent rate, the data capturing rate may be slower or faster depending upon where the data is stored on the disk.
In a CLV storage, the disk spins faster or slower to maintain consistent read/write speeds. The CAV (to maintain consistent angular velocity) needs to have consistent density of tracks and sectors - which hampers their storage capacity. DVDs for example have higher density of tracks and sectors close to the center than the end.
### 2.1.5 Host-Attached Storage (HAS)
They use various I/O busses to fetch data from a HDD or other storage device on the machine at that point. These are usually ***IDE*** or ***ATA***. But a newer branch has evolved which is ***serial ATA*** (often abreviated to ***SATA***)

Servers use SCSI - which can accomodate 16 devices per bus compared to ATA's 2.
16 devices include one controller card (the host) and upto 15 storage devices.

Some Servers may also use Fiber Channel (FC) is an extremely fast speed serial architecture which uses Fiber Optic (also called "Optic Fiber" or "Fiber") cables. One of its variants is quite large switched fabric having 24-bit address space. The other is considered the future of SANs (Storage-Area Networks). Another variant (currently in development) is ***FC-AL*** where ***AL*** stands for ***arbitrated loop***. It can address 126 devices and controllers at the same time.
### 2.1.6 Network-Attached Storage (NAS)
At the cost of speed, it is a storage system which allows users to access the storage over Wi-Fi networks! (Sometimes LAN but generally WLAN or Wi-Fi)
It essentially allows users to create their own Cloud Service in their home. There are many people who have even hosted their NAS for their family (and neighbours too if they pay).
The User who wishes to implement the NAS at their home needs to implement their own RAID structure as well.
### 2.1.7 Storage-Area Networks (SANs)
A major downfall of NAS is that the storage systems consume data bandwidth. Large Clients avoid NAS for this reason. This problem is solved by SANs by using a private network (instead of a Network one).
SANs allow multiple hosts to connect with multiple storage devices attached on the same SAN using a SAN switch.
If one of the users is running out of disk space, a SAN can be reconfigured to provide extra storage to that user.
FC is the most common SAN interconnect, althorugh the simplicity of i-SCSI is increasing its adoption. (iSCSI or i-SCSI is the IP protocol using version of regular SCSI).
## 2.2 Magnetic Tapes
Old Secondary-Storage medium. Although it is relatively permanent and can hold large quantities of data, its access type is slow compared to a Magnetic Disk. Random Acess Time in a tape is 1000 times slower than a disk, hence it is generally used as a more permanent backup medium today due to its slower spinning rate causing less wear and tear on the drive.
# 3. List of Disk Scheduling Algorithms
## 3.1 First Come, First Served Scheduling (FCFS)
- Simplest form of Disk Scheduling
- Intrinsically Fair, but not the fastest option.
- Check [[Process Scheduling#3.1 *First-Come, First-Served Scheduling (FCFS)*\|Process Scheduling#3.1 *First-Come, First-Served Scheduling (FCFS)*]]
## 3.2 Shortest Seek-Time First Scheduling (SSTF)
- The request closest to the the read-write head's current position is serviced first.
- It selects the request with the least Seek Time (see [[Secondary Storage Structure#^3\|#^3]]) from the current head position.
- Better Performance but may cause Starvation.
## 3.3 SCAN Scheduling
- Also called Elevator Scheduling.
- Goes from the starting position to one of the ends of the disk.
- It can only change directions once it reaches one of the ends of the disk.
- Example: Assuming Head starts at 53,
  53, 66, 78, 92, 140, EOD, 15, 10, 5, 1
## 3.4 C-SCAN Scheduling
- Similar to SCAN.
- C-SCAN means Circular SCAN.
- When the head reaches one of the ends of a disk, it wraps to the other end to service requests in the opposite direction.
- Example: Head starts at 53, then goes to 66, 78, 92, 140 and all requests to the right of 53. To change directions, it will go to the end of the disk and then jump straight to 0 and the serve all the requests between 0 and 53 in one go.
- Result: 53, 66, 78, 92, 140, EOD, 0, 1, 5, 10, 15. (where EOD is end of disk)
## 3.5 LOOK Scheduling
- Enhanced version of SCAN
- Goes from the starting position in a given direction but does not go to the end of disk.
- Changes direction as soon as all requests on one side are served.
- Example: 53, 66, 78, 92, 140, 15, 10, 5, 1.
## 3.6 C-LOOK Scheduling
- Enhanced version of C-SCAN.
- C-LOOK means Circular LOOK.
- When the head wraps up the requests on one end, it changes direction and goes to the first request from the other direction.
- Example: 53, 66, 78, 92, 140, 1, 5, 10, 15.
## 3.7 How to select the best?
Two words: Performance and Types (i.e., Types of requests)
Continuous data retreival may be easier for FCFS and SSTF due to the close density of requests.
Far-flung requests may be handled better by SCAN-based or LOOK-based Scheduling methods.
For a general-purpose use such as HDDs and DVDs, they use SSTF or LOOK as default.
Some higher end drives may have multiple options which are chosen by on-board calculations done by the Drive's controller chip.
# 4. What are RAID Structures? How many RAID Levels exist?
- RAID refers to Redundant Arrays of Independent Disks (RAIDs).
- They are commonly used to address the performance and reliability issues.
- They are used for cases where multiple disks may be being used in parallel.
- We store extra informations that is not normally needed but will be useful in a situation where a disk fails and the data needs to be rebuilt. 
- Even if the disk fails, data is not lost.
## 4.1 Non-Volatile RAM (NVRAMs)
- The write-back cache is protected from data loss during power failures, so the write can be considered complete.
- Very useful in places with commonly known infrastructure issues or places prone to natural calamities.
## 4.2 RAID Levels
Read Section 11.8.3 (Pages 599-609) on the [[Operating System Concepts - 2018.pdf]] for in-depth explanation.

- ***RAID 0*** allows only for Striping ([[Secondary Storage Structure#^4a\|#^4a]])
- ***RAID 1*** allows only for Mirroring ([[Secondary Storage Structure#^4b\|#^4b]])
- ***RAID 4*** allows striping and 1 disk for storing parities only. Meaning, if you have 9 disks, this method will reduce it to 8. Parities help recover the stripes lost. ([[Secondary Storage Structure#^7\|#^7]])

***==Big Question==: While using RAID 4, what if the Parity Disk is the one that fails?***
Where RAID 0 does not provide any Fault Tolerance ([[Secondary Storage Structure#^5b\|#^5b]]) and RAID 1 halves the disk space, RAID 4 seemed a great idea but this question caused the creation of RAID 5.

- ***RAID 5*** allows Parity blocks are distributed across all 9 disks. 
- If one disk fails, the data on that disk is lost, but the parity information can be used to reconstruct the lost data.
- Here's an example of how the parity blocks may be distributed across the disks in a 9-disk RAID 5 array:
	- Data for Stripe 1: Disk 1
    
	- Parity for Stripe 1: Disk 2
    
	- Data for Stripe 2: Disk 2
    
	- Parity for Stripe 2: Disk 3
    
	- Data for Stripe 3: Disk 3
    
	- Parity for Stripe 3: Disk 4
    
	- ... and so on, with the pattern repeating every 9 stripes.

***==Big Question==***: Since there is only 1 parity block per stripe, hence what if more than one disk fails?
This Question gave rise to RAID 6.

- In ***RAID 6***, the parity information would be distributed across two disks, rather than just one as in RAID 5. This provides additional fault tolerance by allowing for the failure of up to two disks without losing data.
- Here's an example of how the parity information might be distributed across the disks in a 9-disk RAID 6 array:

	- Data for Stripe 1: Disk 1, Disk 2
    
	- Parity for Stripe 1: Disk 3, Disk 4
    
	- Data for Stripe 2: Disk 2, Disk 3
    
	- Parity for Stripe 2: Disk 4, Disk 5
    
	- Data for Stripe 3: Disk 3, Disk 4
    
	- Parity for Stripe 3: Disk 5, Disk 6
    
	- ... and so on, with the pattern repeating every 9 stripes.

- If one of the disks in the array were to fail, the data could be reconstructed from the remaining data and parity information on the other disks. If two disks were to fail, as long as they were not the same disk from each parity block, the data could still be reconstructed.
- This added level of fault tolerance comes at the cost of some storage capacity, as two disks are used for parity information instead of just one. However, for mission-critical applications where data availability is paramount, the added protection provided by RAID 6 can be worth the trade-off.

Only RAID 10 and RAID 0+1 is left.
RAID 0+1 strips first and then mirrors the individual disks.
RAID 1+0 (i.e., RAID 10) mirrors the disks (9 disks become 18) and both those sets are striped in an array. RAID 10 is considered more robust than RAID 0+1.
Similarly RAID 50 and 60 also exist using similar logic.
## 4.4 Problems with RAID
- RAID can very easily fail in cases where a pointer to a file may be wrong or incomplete writes (which couldn't be recovered) can cause corrupted data
- Natural Disasters can end all the disks in one sweep.
- As disks get older, other disks can fail as the faulty one repairs...

# Footnotes
- ***Track*** is the circular lane in a magnetic platter where data is stored. It is divided into smaller sub-divisions known as a ***Sector*** individually, and *sectors* collectively.
{ #1}

- "Difference between a CAV and a CLV type storage" - [Comp-Sci Station Website](https://compscistation.com/cav-vs-clv/)
{ #2}

- ***Seek Time*** is the time for the disk arm to move the heads to the cylinder containing the desired track and sector.
{ #3}

- ***Rotational Latency*** is the additional time for the disk to rotate the desired sector to the disk read-write head.
- ***Bandwidth*** is total number of bytes transferred, divided by the time between the first request and the completion of the last transfer.
- ***Striping***: A process of dividing the storage into segments (called blocks) and storing each block on separate disks to increase performance.
{ #4a}

- ***Mirroring***: A process of keeping multiple synchronus/synchronised copies of the same data on more than 1 disk to account for backups in case a disk fails. (A type of [[Secondary Storage Structure#^6b\|#^6b]])
{ #4b}

- ***Faults***: A hardware or software fault can induce system crash, disk data loss.
{ #5a}

- ***Fault Tolerance***: The ability of a system to automatically detect & recover from faults and continue functioning even in the presence of hardware or software failures. Achieved by replication, redundancy among others.
{ #5b}

- ***Redundancy***: Using multiple components (here, disks) in place of one to use if one of them fails.
{ #6a}

- ***Replication***: A process of keeping multiple copies of data on separate disks (may be synchronus, generally asynchronus).
{ #6b}

- ***Parities (AKA Parity Blocks)***: A parity block is a type of data block used in RAID configurations to provide fault tolerance and is used to reconstruct data in case the disk fails. It is calculated by performing an XOR operation on the data blocks stored on the disk array.
{ #7}


