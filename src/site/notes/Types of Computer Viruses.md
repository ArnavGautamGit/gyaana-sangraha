---
{"dg-publish":true,"permalink":"/Types of Computer Viruses/","tags":["CyberSec","CompSci"]}
---


---
# Types of Computer Viruses
[[Computer Virus\|Computer Viruses]] can be typed on the basis of a multitude of factors which can decide or change classification.

Any Virus can be typed based on 3 categories:
- Activity
- Targets
- Concealment

---
## Types of Viruses based on ==*Activity*==
The Virus when it enters the system is either a 
1. Transient Virus 
2. Resident Virus. 
Resident one is the one (as the name implies) that stays. Resident one wants to get into your internal/main/RAM memory. Transient one works similar to the host program it attached to, it can only stay on as long as its host program is on.

| Resident | Transient |
|-----|-----|
| Locates itself in memory or (C:) Drive |  Attaches itself to a program in (D:) drive |
| Can remain active as a standalone program | Only active when the host program is active |

---
## Types of Viruses based on ==*Targets*==
There are 4 types here:
1. ==***Boot Sector Infector***==: Attacks the Bootstrap (hence aka 'Bootstrap Destroyer') placed inside Boot Sector. It is an interface between the ROM and the OS used to boot the OS. Without the OS, modern systems cannot function.
2. ==***File Infector***==: Common. It has an intention of attacking certain file or group of files - generally the system files inside the C: Drive on your computer and destroy your RAM and similar components.
3. ==***Macro Viruses***==: Affects the functioning of automated functions. The functionality of adding custom Fonts in MS Offics was heavily used by Macro Viruses as a vulnerability which grants access directly to your computer's C: Drive.
4. ==***Multipartite Virus***==: a type of computer virus that harms the files of computers, systems or devices and attacks both the boot sector and the executable files.
---
## Type of Viruses based on ==Concealment==
There are again 4 types:
1. Encrypted Viruses
2. Stealth Viruses
3. Polymorphic Viruses
4. Metamorphic Viruses
We cannot summarise any one of these in the same line because of how each of these contain a layer - of a concept we need to learn first. Example: We need to learn Metamorphism before Metamorphic Viruses.
### 1. Encrypted Virus
We have to first understand Encryption and what it does.
*==Encryption==* is a process by which the contents of a piece of text (message, letter or code) can be modified or change to make it unreadable by conventional means or by laymen. Only a person who can *decrypt* the code using a *key* can read it. It is preferred that the decryption is performed by the intended reader of the text. 
An ==Encrypted Virus== converts itself to a form not readable by conventional means, hence its signature cannot be identitfied by most anti-virus softwares and it can maintain stealth.
As it is a virus, it spreads by multiplying... ==A good encrypted virus makes sure that in each replication, the virus creates a new encryption (preferably harder than before) and a new key which is stored inside the virus itself==.
### 2. Stealth Virus
Designed to hide itself from detection by using compression and *code mutation*.
Code Mutation is a technique used by a virus to edit its own code!
The Virus edits its own code, jumbles functions up and down to change its signature and maintain stealth.
### 3. Polymorphic Virus
==*Polymorphism*==: Singular entity taking different/multiple forms. For Example: Hinduism is a polymorphic religion.
In the case for Viruses, A polymorphic virus is designed to change its signature (using Code Mutation) regardless of replicating currently or not. The replica (obviously) will have a different signature.
==Advanced Polymorphic Viruses are able to replicating in such a way to change their signatures to something never seen before. Many are able to change their distinct bit patterns to maintain stealth==. 
### 4. Metamorphic Virus
It mutates with every infection and replication.
Has the ability to re-write itself completely.
Can change behaviour and appearance
Break it into 100, you create 100 viruses.

---
# Footnotes