---
{"dg-publish":true,"permalink":"/Data Anonymisation/","tags":["Academics","CyberSec","Software-Development"]}
---


---
# Data Anonymisation
> The Process of alters all [[Identifiers & Quasi-Identifiers\|Identifiers & Quasi-Identifiers]] from a [[Data Mining\|mined]] dataset to provide [[Data Privacy\|Data Privacy]] to all users.

It is one of the most important parts of [[Data Mining\|Data Mining]] so that the [[Data Buyer\|Data Buyer]] (company this data is going to be sold to) should not be able to trace the users and violate their privacy by providing unsolicited opinions/advice/advertisements.

Example: Given a Data Set of a hospital, one would not want to disclose whether they have a particular disease, but if that data is used by the company as it is (by not [[Data Anonymisation\|Anonymising]]) then the data can eventually trace back to the person who provided the data or the companies who get hands on that data could send promotional products to the user's address.

### Anonymisation Operations
There are many operations by which a dataset is render completely Anonymised:
1. [[Generalisation\|Generalisation]]: replaces some values with a parent value in the Classification of an attribute into classes.
2. [[Suppression\|Suppression]]: replaces some values with a special value to hide the original value.
3. [[Anatomisation\|Anatomisation]]: does not modify the quasi-identifier or the sensitive attribute, but de-associates the relationship between the two.
4. [[Permutation\|Permutation]]: de-associates the quasi-identifier with a numerically sensitive values by shuffling the values randomly within the same group.
5. [[Perturbation\|Perturbation]]: replaces original numerical values with new values that do not cause as much statistic distortion.
6. [[Bucketisation\|Bucketisation]]: grouping of similar data to break the relation b/w Quasi-Identifier and Sensitive Attribute.

It is also important to be noted that [[Too Much of Anything is Dangerous\|Too Much of Anything is Dangerous]] and hence, too much Anonymisation may render the data un-analysable because it is too far anonymised that any reasonable inference that could be drawn from it is now gone. So Anonymisation needs to be done with respect to what that data is being readied for. This reduction in data utility is known as *"**Information Loss**"*.

### Anonymity Models
There are various models developed to attain different levels and types of Data Anonymisation. Some of them are:
- [[K-anonymity\|K-anonymity]]: Data of one tuple is made to look exact to the other k-1 tuple except the main attributes along which we need to compare the dataset.
- [[L-diversity\|L-diversity]]:
- [[T-closeness\|T-closeness]]:
- [[Epsilon-differential privacy\|Epsilon-differential privacy]]:

The reality is that no matter how much we try, unless we use [[Data Pseudonymisation\|Data Pseudonymisation]], we cannot reduce Information Loss & it can never be 0% anyway - unlike Pseudonymisation which replaces identifiers with pseudonyms. It allows for retaining information and data accuracy while protecting [[Data Privacy\|Data Privacy]] to some degree.  

---
# Footnotes