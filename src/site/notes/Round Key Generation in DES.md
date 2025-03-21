---
{"dg-publish":true,"permalink":"/Round Key Generation in DES/","tags":["CompSci","CyberSec"]}
---


---
# Round Key Generation in DES
Using the [[DES Master Key\|DES Master Key]] of the Cipher, which is of 64 bits, we can build multiple Round Keys using one of the [[Round Key Generator Algorithms\|Round Key Generator Algorithms]] which is specialised for the [[DES (Data Encryption Standard)\|DES (Data Encryption Standard)]].

### Algorithm
- We use 64-bit Cipher key and put it through a Parity Drop Algorithm i.e., the LSB bit of each 8-bit block is dropped - leaving us with 56-bits (8 blocks of 7-bits each).
- The 56-bit key is now divided into 2 halves of 28 bits each (4 blocks of 7-bits each).
	- Left Half is shifted left.
	- Right Half is shifted right.
	- Both shifted keys are placed into a [[DES Compression P-Box\|DES Compression P-Box]].
	- The Output is the one of the [[DES Round Keys\|DES Round Keys]] for R1.
	- For Round 2, we use the left & right shifted 28-bit halves from the last round and left shift the left side, right shift the right side & slap it into the next [[DES Compression P-Box\|DES Compression P-Box]].

---
# Footnotes