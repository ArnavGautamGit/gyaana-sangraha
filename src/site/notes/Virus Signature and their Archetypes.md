---
{"dg-publish":true,"permalink":"/Virus Signature and their Archetypes/","tags":["CyberSec","CompSci"]}
---


---
# Virus Signature and their Archetypes
- A Virus cannot be completly invisible
- Code must be stored somewhere
- Each of the telltale signs put together is termed as "signature". Think of it as a pattern which is used by Anti-Virus Software to detect Viruses.
- Anti-Virus Softwares are just programs which have all the KNOWN signatures and has the ability to search your PC for Viruses. It can also delete them, but would need your permission to do so.
- Anti-Virus Softwares only contain known signatures, so novel viruses are still a threat.
### Signature Archetype 1: ==Compression Virus==
If the host program is 300MB, the virus is 30MB, then it attaches itself and compresses the host to 270MB. It can be agressive compression which means the virus deletes the 30MB worth of .dll files.
So that once the virus has attached, the program is again 300MB and the user does not suspect anything.
### Signature Archetype 2: ==Integrated Virus==
The Virus has the ability to dissolve itself into individual functions and imbed itself as spread-out pieces in the original program. Read more on Wikipedia
### Signature Archetype 3: ==Macro Virus==
- Macros are used to automate repetitive tasks to save key strokes.
- Macros are also used to support dynamic content, form validation etc.
- Macro *Viruses* infect scripting code used to support active content (MS Office fonts, PDF readers scripting code etc.)
- Macro Viruses are platform independent
- MVs spread via email or wherever attachments can be attached with a message.
### Countermeasures to Macro Viruses
- MS Office increased protection.
- Anti-virus softwares have been updated.
- Adobe pdf viewer includes warning measures and warns users when they open a pdf for the first time after it just got downloaded.

---
# Footnotes