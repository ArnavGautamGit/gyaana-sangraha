---
{"dg-publish":true,"permalink":"/Round Function of DES/","tags":["CompSci","CyberSec"]}
---


---
# Round Function of DES
> [[Round Function\|Round Function]] used in [[DES (Data Encryption Standard)\|DES (Data Encryption Standard)]] inspired by the [[Substitution-Permutation Network\|SPN]].

The Algorithm utilises the [[Expansion P-Box\|Expansion P-Box]], and the [[Straight P-Box\|Straight P-Box]] along with [[S-Boxes of DES\|S-Boxes of DES]].

### Algorithm
- As we saw in the main algorithm of the [[DES (Data Encryption Standard)\|DES (Data Encryption Standard)]], the 64-bit Plaintext is split into two halves of 32-bits.
- Since these halves are actually very small, we put them into the [[Expansion P-Box\|Expansion P-Box]], which has 16 repeating bits so that there are 48 table entries, which means it will expand the plaintext to 48-bits.
- The output would be in 8 blocks of 6-bits. Each of the 6-bits are going to be placed through a singular [[S-Boxes of DES\|S-Box]] which will take the MSB and LSB to point to the row, while the other 4 point to a column. Together they point to a specific coordinate.
- This Coordinate replaces the 6-bit input as the 4-bit output.
- This Process is repeated throughout the eight S-Boxes (which remain the same across all the 16 rounds).
- After the output of the S-Box is received, to avoid the same substitution running in all rounds, we use a [[Straight P-Box\|Straight P-Box]] to spread the keys around so that they go through as many S-Boxes as possible.
- Output of the $\large n^{th}$ round is the input for the $\large (n+1)^{th}$ round.

---
# Footnotes