---
{"dg-publish":true,"permalink":"/Data Pseudonymisation/","tags":["Academics","CyberSec"]}
---


---
# Data Pseudonymisation
> Process to protect [[Data Privacy\|Data Privacy]] during the process of [[Data Mining\|Data Mining]] without losing important patterns in the data which companies and researchers may be interested in. 

The Loss of information is never 0% but since the pseudonyms are consistently mapped, it will retain any data patterns i.e., Data remains valuable when all instances of the same data are given the same pseudonym.

### Weakness
The major problem here is its inherent weakness similar to [[Ceaser Cipher\|Ceaser Cipher]] which easily breaks if the attacker realises all the alphabets are shifted by the same amount, if the attacker is able to break the logic with which Pseudonyms are assigned, then they may be able to intrude on the user's [[Data Privacy\|Data Privacy]]. 

A quick but naïve solution is to avoid OBVIOUS patterns between the original data and the Pseudonyms used for that data. There may be a pattern but it must not be easily predictable.

### Present Solution
Using the principles of [[Pseudonymisation of Information for Privacy in e-health (PIPE)\|Pseudonymisation of Information for Privacy in e-health (PIPE)]].
It uses the concept of [[Substitution-based Ciphers\|Substitution-based Ciphers]] but with the [[Cryptographic Key\|Cryptographic Key]] being a collection of Pseudonyms used to replace respective attributes that the Pseudonyms pertain to. There is very basic amount of [[Data Anonymisation\|Data Anonymisation]] where Primary Identifiers (such as name and address) are removed.

---
# Footnotes