---
{"dg-publish":true,"permalink":"/Bucketisation/","tags":["Academics","Software-Development","CyberSec"]}
---


---
# Bucketisation
> A Technique used for [[Data Anonymisation\|Data Anonymisation]] which protects [[Data Privacy\|Data Privacy]] by grouping continuous data into discrete bins or categories. This transformation helps to obfuscate individual values while maintaining useful patterns for statistical analysis.

The aim is to not let users be identified based on their exact individual data points but let the users be identified in groups like Low, Middle and High Income (example).

We identify the continuous attribute that we wish to Anonymise, define buckets and assign data to buckets.

### Advantages
- Simple and Efficient
- Data Utility is preserved
- Prevents Re-identification if bucket range is wide
- Enhanced Privacy

### Disadvantages
- Precision Loss
- Vulnerability to Re-identification if buckets are narrow
- Risk of Over-generalisation (risk of loss of utility)
- Decreased Accuracy in some cases

### Best Practices
- Choose Bucket Size Wisely
- Combine with other techniques
- Assess Re-identification Risk
- Consider Data Sensitivity.


---
# Footnotes