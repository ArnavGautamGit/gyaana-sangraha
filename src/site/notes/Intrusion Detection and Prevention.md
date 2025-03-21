---
{"dg-publish":true,"permalink":"/Intrusion Detection and Prevention/","tags":["Academics","CyberSec"]}
---

***Created on: 31/10/2023
Last updated: 06/12/2023***

----
# Index/Contents
[[Intrusion Detection and Prevention#1. What is Intrusion?\|#1. What is Intrusion?]]
[[Intrusion Detection and Prevention#2. What should an IDPS be able to do?\|#2. What should an IDPS be able to do?]]
[[Intrusion Detection and Prevention#3. Various Classification of IDS Softwares\|#3. Various Classification of IDS Softwares]]
[[Intrusion Detection and Prevention#Footnotes\|#Footnotes]]

-----
# 1. What is Intrusion?
*Actions aimed to compromise the security of the system or any of its parts*.
Examples: Unauthorised Login, Worm Injection, Spyware injection, flooding etc.
## 1.1 How is Intrusion Detected?
Intrusion can be detected only by monitoring the network and the data flowing through it... otherwise how will the system knows what is an anomalous behaviour and what isn't?
IDS (Intrusion Detection System) keeps tabs on multiple things in the network or system. Things like Number of ARP requests, Ratio of TCP SYN to TCP FIN packets etc.
## 1.2 How is Intrusion Prevented?
The IPS (Intrusion Protection System) needs to have access of large volumes of data along with the power of suspending IP, Port and MAC addresses if needed... It needs to have the power to terminate specific programs/threads by isolating the specific infected PC or something similar.
## 1.3 What system is used for Intrusion Detection and Prevention?
Earlier IDS and IPS were used separately but now there are more and more programs that have both detection and prevention abilities combined. These are called Intrusion Detection and Prevention System (IDPS).

---
# 2. What should an IDPS be able to do?
Access Rights of an IDPS.
For best/optimum functioning, the IDPS needs to be able to:
1. ***==Access large volumes of network traffic==*** or system activity to find signs of any unauthorised access on any of the systems.
2. ***==Record its findings and collected data==*** as logs so that system admins can examine past activity as well. There may be activity happening in the off-hours that they need to check to ensure no attack happenend in the night.
3. ***==Detect and Record unauthorised access==*** and send it to the IRS ([[Intrusion Detection and Prevention#^1\|#^1]]) or the Intrusion Response Team ([[Intrusion Detection and Prevention#^2\|#^2]]). The recording aspect is important evidence in court.
4. Respond almost immediately
5. Make itself and systems it protects as absolutely inaccessible as possible.

---
# 3. Various Classification of IDS Softwares
In [[Intrusion Detection and Prevention#1.1 How is Intrusion Detected?\|#1.1 How is Intrusion Detected?]] we learned what an IDS is and How are Intrusions detected. Here we learn the various kinds of IDS Softwares available.

>*(Note: Many of these IDS Softwares may also use "hardware" devices, like physical attachments to the Router, but the Software part is what does the detection)*

All technologies need a basis of classification to compare, select and improve upon technology. So that a client can compare which kind of IDS they need and the devs know what exactly to improve.
Discussed further in the course, we shall see different basis of classifying Detection Systems:
 - On the Basis of Detection Models
 - On the Basis of Deployment Location
 
 > *(Note: We should use both of them (and all of their subclasses) together for maximum security. Some workplaces, like the DRDO don't even allow the users to carry their phones.)*
## 3.1 Classification on the basis of ==Detection Models==
| ***MISUSE DETECTION*** | ***ANOMALY DETECTION*** |
|---|---|
| Also known as "Signature-based". | Also called as "Statistic-Based" |
| Each Malware has a Signature. Similarly, there are signatures of network attacks. It scans for such signatures and access demands. | Average/normal function is identified, any variance in any parameter beyond the threshold is considered anomalous. It scans for such anomalies |

> ###### ***Challenges faced by Signature-Based Detection Models***
> - Weak against Zero-Day Attacks
> - Suffers from False Alarms.
> - Need to be prgrammed again for every signature is found.
## 3.2 Classification on the basis of ==Deployment Locations==
| ***HOST BASED*** | ***NETWORK BASED*** |
|---|---|
| Placed at the Host Location (inside each user system) | Placed near the Router or Switch (common for all user systems) |
| Used for companies which often work remote | Used by Universities and Firms alike since it is built for closely-knit wired connections |
| Protects Individual | Protects the entire Network |

## 3.3 Experimental Approach: File Access Based Anomaly Detection Technique
There are three main variables to consider. H-values, A-values and S-values.
H-values refer to the Historical/Heuristic values A-value refer to the Access Value (Current).
S-value is the shortform for Statistic.
For a given user, there are two tables given, one for H and other for A values
The 2 tables are:
Table 1:

| $\large H_0$ | $\large H_1$ | $\large H_2$ | $\large H_3$ |
|---|---|---|---|
| 0.10 | 0.40| 0.40 | 0.20 |

and Table 2:

| $\large A_0$ | $\large A_1$ | $\large A_2$ | $\large A_3$ |
|---|---|---|---|
| 0.10 | 0.40| 0.30 | 0.15 |

Also, remember two formulae
$\large S = {(H_0 - A_0)}^2 + {(H_1 - A_1)}^2 + {(H_2 - A_2)}^2 + {(H_3 - A_3)}^2$ 
and
$\large H_i = 0.2\times A_i + 0.8\times H_i$
Unless it is given otherwise, as long as $\large S<0.1$, the access is considered normal.  

The question is simple: How to solve?
1. Use the first formula to find S using H and A values.
2. Use the second formula for $\large H_i$ to find updated H-values.
3. Update the H-values.
4. Iterate points above for as many cycles as the question demands.
### 3.3.1 Problem with this System
30 mins to an hour later, after 2-3 iterations of this method, the access will always be deemed anomalous since the base values of at least one H-value will be $\large \geq 0.1$
### 3.3.2 My Proposed Solution
Reset H-values in the next day (at next shift start)
Or use another anomaly/misuse detection software to crosscheck before raising an alarm.
Or raise the anomaly level be raised after each iteration, so it goes from $\large 0.1 \ \text{to} \ 0.2$ and so on.

---
# 4. Stateful Protocol Analysis
Stateful Protocols are those which can save the state of any program (example: Cookies)
Spyware can usually be concealed under such protocols hence why people are anti-cookies.

These Protocols however, use State Tables. They contain the state of multiple programs in the form of a table.

SPA uses:
- Traffic Rate Monitoring
- Protocol State Tracking
- Dynamic Application protocol Analysis
- IP Packet reassembly i.e., it can re-assemble the packet if needed [[Intrusion Detection and Prevention#^3\|#^3]]
{ #Reassembly}


---
# Footnotes
- ***Intrusion Response System***. A computer automated version of an IR Team. Works to respond in kicking out or destroying the threat on the system while collecting and recording information that can be used as evidence in Courts
{ #1}

- ***IR Team*** is a team of humans working on kicking out or destroying any attack on their system or network. Most teams have been replaced by (or at least supplemented with) a computer-based IRS since they can defend just as well in the night as in the day since they don't need to change shifts neither do they get tired. As long as it is fine by the company policy, (or they are not in a company at all!) IR Teams are seldom condiered more dangerous since they can and will be responsible for any counter-attack.
{ #2}

- ***IP Packet Reassembly*** is a technique that is used in networks. Datagrams (also called data packets) don't travel in one single piece, after fragmentation on the sender's end, the Datagram's separate pieces may take separate routes to reach the destination and hence needs to be reassembled at the destination. IPPR does the reassembly and even cross-checks it.
{ #3}
