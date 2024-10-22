---
{"dg-publish":true,"permalink":"/Static Application Security Testing/","tags":["Academics","CyberSec","Software-Development"]}
---


---
# Static Application Security Testing
> It is a process of using a software tool to examine the code and check for any [[Cyber Security Terminology#Vulnerabilities\|vulnerabilities]] in your code and try to find faults in the system, any exploitable gaps etc.

SAST is the backbone of contemporary secure application development. The only thing that holds it back is that Good SAST tools cost quite some money are access to them is often limited by ther presence of only an enterprise license (not available for personal use).
### Advantages
Since any SAST Tool examines code, it does not need a running app and can be performed very early in the [[Software Development Life Cycle\|SDLC]] as well. It has the advantage that one would not have to break any builds & [[Cyber Security Terminology#Vulnerabilities\|vulnerabilities]] can be sorted as we go. 

SAST Tools help in preventing Security Issues becoming an after-thought. The tools are a lot more easier to use that scouring through books or [[Stack Overflow (Website)\|Stack Overflow (Website)]] & do not require domain expertise.

Good tools offer graphical representations of most-common vulnerabilities, exact ocation of the vulnerability in code along with best path to fix it and the option to create customised reports to download offline.

### Popular Tools
Many popular tools exist on the market for SAST puposes including ***==Klocwork==*** (C/C++ and Java), ***==SpectralOps==*** (Multi-language, centred around keys and APIs), ***==Checkmarx==*** (even works with graphs), ***==Veracode==***, ***==LGTM==***, ***==Coverity==***, ***==Code Sight==*** etc.

### Detailed Process
1. Chose and FInalise the Tool.
2. Create a Scanning Infrastruture & Deploy Tool.
3. Customise Tool.
4. Prioritise on-board apps.
5. Analyse Scan Results.
6. Provide Governance and Training.


---
# Footnotes