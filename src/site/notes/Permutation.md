---
{"dg-publish":true,"permalink":"/Permutation/","tags":["Academics","Software-Development","CyberSec"]}
---


---
# Permutation
> A [[Data Anonymisation\|Data Anonymisation]] scheme used to protect [[Data Privacy\|Data Privacy]] by shuffling the Sensitive Attributes randombly and hence breaking their relation and linkage with [[Identifiers & Quasi-Identifiers\|Identifiers & Quasi-Identifiers]]. 

Due to Permutation, we store a Cancer patient's disease as Flu but it is only done for old data to be provided for research. This stupidity of the idea is why no one will expect this method to be used - enhancing the privacy it provides.

### Advantages
- Preserves Data Utility
- Simple Implimentation
- Enhanced Privacy

### Disadvantages
- Risk of Linkage Attacks: if the attacker knows the original order, the plan fails spectacularly.
- Limited Protection for small datasets since the order is easy to crack.
- Attribute Independence Assumption ([[Permutation#^1\|#^1]])

### Best Practices
- Combine with other techiques
- Test for Re-identification Risk.
- Limit Data Releases
- Aggregate Analysis


---
# Footnotes
1. If the researcher needs to research the relation between geographical location and the likeliness to develop a particular kind of disease, then the shuffling renders data absolutely useless. We assumed that the attributes will not be related when providing the data to [[Data Buyer\|Data Buyer]] which is not always true.
{ #1}

2. 