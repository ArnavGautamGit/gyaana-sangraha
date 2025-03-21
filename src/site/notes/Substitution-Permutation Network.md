---
{"dg-publish":true,"permalink":"/Substitution-Permutation Network/","tags":["CompSci","CyberSec"]}
---


---
# Substitution-Permutation Network (SPN)
> [[Iterative Product Cipher\|Iterative Product Cipher]] Network that uses Substitution and Permutation on the entire Plaintext at once. 

When it was first published, it was thought to be less practical than [[Feistel Network\|Feistel Network]] due to hadware limitations. It is not the case today.

1. Plaintext is taken from the user, it is XORed with a "Round Key" ([[Substitution-Permutation Network#^1\|#^1]])
2. The resultant is divided into smaller blocks in order, and then sent to their repective [[S-Box\|S-Box]].
3. [[P-Box\|P-Box]] takes all S-box outputs & jumbles the blocks deteministically.
4. The output is the output of Round 1 (R1).
5. The Output of $\large n^{th}$ round is used as input for the $\large (n+1)^{th}$ round

---
# Footnotes
1. ***Round Key*** is derived from taking a small part of the full [[Cryptographic Key\|Cryptographic Key]] using [[Round Key Generator Algorithms\|Round Key Generator Algorithms]]
{ #1}

2. Input maybe expanded or reduced to match the key size.