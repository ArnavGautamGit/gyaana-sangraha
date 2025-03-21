---
{"dg-publish":true,"permalink":"/S-Boxes of DES/"}
---


---
# S-Boxes of DES
> [[S-Box\|S-Boxes]] used in [[DES (Data Encryption Standard)\|DES (Data Encryption Standard)]] which take an input of 6-bits and gives an output of 4-bits.

Used after division of 64-bit Plaintext (8 blocks of 8-bits each) into two halves of 8 blocks of 4-bits each (32-bits).

### Working
After the Expansion, we obtain 8-blocks of 6-bits each
Each of the 6-bits are going to be placed through a singular [[S-Box\|S-Box]] which will take the MSB and LSB to point to the row, while the other 4 point to a column. Together they point to a specific coordinate. This Coordinate replaces the 6-bit input as the 4-bit output.



---
# Footnotes