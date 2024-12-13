---
{"dg-publish":true,"permalink":"/Anatomisation/","tags":["Academics","Software-Development","CyberSec"]}
---


---
# Anatomisation
> A [[Data Anonymisation\|Data Anonymisation]] technique used in [[Data Privacy\|Data Privacy]] used to separate Sensitive Attributes from [[Identifiers & Quasi-Identifiers\|Quasi-Identifiers]] & stores them in distinct datasets.

It works by splitting the data into $\large \geq 2$ parts and then decoupling the records to prevent linkage between the QIDs and Sensitive Attributes. Probabilistic Associations are retained, however.

### Advantages
1. Preserves Data Utility
2. Enhanced Privacy
3. Easy/Simple compliance with GDPR, HIPAA and other Privacy Laws

### Disadvantages
1. Re-identification risk if some attacker got hands on both tables.
2. Complex to implement.
3. Limited use cases - not as versatile technique as others. 

### Best Practices
1. Regularly check for re-identification risks with each data release.
2. Use Access Controls to limit access to both tables only to the authorised.
3. Combine with other techniques (such as [[Generalisation\|Generalisation]] and [[Suppression\|Suppression]]).

---
# Footnotes