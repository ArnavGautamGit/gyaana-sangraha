---
{"dg-publish":true,"permalink":"/Perturbation/","tags":["Academics","Software-Development","CyberSec"]}
---


---
# Perturbation
> A technique used for [[Data Anonymisation\|Data Anonymisation]] which protects [[Data Privacy\|Data Privacy]] by altering data values in a controlled way to prevent the identification of individuals while retaining the overall statistical properties of the data.

Instead of deleting or generalising values, we modify the dataset to add noise in a controlled manner along with minor changes, The goal being preservation of utility by making it harder for the attacker to reverse-engineer this process.

### Types
- Noide is ***added*** to the dataset. (Additive)
- A random ***multiplier*** is applied to data values. (Multiplicative)
- Values are ***swapped*** amongst records (Swap)
- Values are ***rounded off*** to obscure exact values (Rounding)

### Advantages
- Preserves Data Utility
- Enhanced Privacy
- Flexibility
- Real-Time Use

### Disadvantages
- Risk of Data Distortion similar to [[Permutation\|Permutation]]
- Reduced Accuracy
- Re-identification Risk 
- Data Correlation which was previously not there.

### Best Practices
- Controlled Noise Addition must be ensured.
- Combination with other techniques.
- Check impact of Noise on Data Utility.
- Tailor Perturbation to Data Sensitivity - don't use for low variance data


---
# Footnotes