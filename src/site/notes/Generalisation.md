---
{"dg-publish":true,"permalink":"/Generalisation/","tags":["Academics","Software-Development","CyberSec"]}
---


---
# Generalisation
> A [[Data Anonymisation\|Data Anonymisation]] technique used in [[Data Privacy\|Data Privacy]] for making it harder to identify individuals in a dataset. It involves replacing specific values of [[Identifiers & Quasi-Identifiers\|Quasi-Identifiers]] with broader, less specific categories or ranges.

It basically involves just generalising the dataset by switching the specific values to more general values or providing a range of values instead

### Types
Generalisation comes in various types:
1. ***Range*** - substitute original value with range. Example: Age "20" becomes "15-25".
2. ***Categorical*** - substitute with a general categorical value like "Cardiologist" is replaced to be "Doctor"
3. ***Hierarchical*** - Mask a certain number of characters according to the level of Generalisation.
4. ***Spatial*** - Replace original value to a more general one like "Rohtak" is replaced with either "Haryana" or "India".

### Benefits of use
1. Preserves Data Utility.
2. Simple to Implement.
3. Supports Data Aggregation for high level trend analysis.

### Limitations of use
1. Loss of precision in data.
2. Vulnerability to Re-Identification.
3. Trade-off between Privacy and Utility.

### Best Practices
- Generalise only as much as needed to clear the Privacy Requirements.
- Combine with other techniques like [[Suppression\|Suppression]] to remove Identifiers like names.
- Test for Re-Identification Risk - can the user be re-identified by a [[Data Buyer\|Data Buyer]]?
- Optimise utility for the dataset by balancing privacy and utilitarian needs.

---
# Footnotes