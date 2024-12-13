---
{"dg-publish":true,"permalink":"/Suppression/","tags":["Academics","Software-Development","CyberSec"]}
---


---
# Suppression
> A [[Data Anonymisation\|Data Anonymisation]] technique used in [[Data Privacy\|Data Privacy]] to protect sensitive information on basis of which users can be identified. It involves outright elimination of [[Identifiers & Quasi-Identifiers\|Identifiers & Quasi-Identifiers]].

There are cases where the removed attribute is replaced with placeholders such as "Null" or "Unknown" or "Redacted".

### Types
Suppression is of various kinds:
- Removing an ***Attribute*** like Dropping the "name" column
- Masking a ***value*** such as GPS location with a placeholder
- Deleting ***records*** which pose a re-identification risk.
- ***Partially*** masks a sensitive attribute like Aadhar number.

### Benefits of use
- High Privacy
- Simple to implement

### Limitations of use
- Incomplete Privacy if QIDs are not properly suppressed
- Prone to Overuse
- Data Utility Loss

### Best Practices
Same as [[Generalisation#Best Practices\|Generalisation#Best Practices]]


---
# Footnotes