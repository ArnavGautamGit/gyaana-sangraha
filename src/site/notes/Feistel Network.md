---
{"dg-publish":true,"permalink":"/Feistel Network/","tags":["CyberSec","Academics"]}
---


---
# Feistel Network
> [[Iterative Product Cipher\|Iterative Product Cipher]] Network that splits the plaintext into two & operates on half of the plaintext in one iteration, leaving the other half to be processed in the next.

When this was first published, it was understood that this is more practical than [[Substitution-Permutation Network\|SPN]] due to hardware limitations. It is not the case today.

1. The Plaintext is split into two halves.
2. One of the two halves (either left or right) will be put through a [[Round Function\|Round Function]].
3. The output of the Round Function is then XORed with the un-touched side.
4. Then the sides are swapped. Left half goes to the right and vice versa.
5. The Output of $\large n^{th}$ round is used as input for the $\large (n+1)^{th}$ round

> ***Note***: These Encryptions are revertible (i.e., Encrypted Data can be Decrypted) even if the Round Function used is irreversible. It is generally advised to make the Round Function as hard as possible.

---
# Footnotes