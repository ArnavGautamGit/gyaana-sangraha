---
{"dg-publish":true,"permalink":"/DES (Data Encryption Standard)/","tags":["CompSci","CyberSec"]}
---


---
# DES (Data Encryption Standard)
> The first among the [[Modern Cryptographic Ciphers\|modern]], [[Substitution-based Ciphers\|substitution-based]], [[Block Ciphers\|Block Ciphers]].
> DES was made in 1977 with the combination of [[Feistel Network\|Feistel Network]] and some inspiration was taken from [[Substitution-Permutation Network\|SPN]] when the [[Round Function of DES\|Round Function of DES]] was designed.

Most Books still refer to it as a Cipher based on a [[Feistel Network\|Feistel Network]] since it is primarily a Feistel Cipher with a Round Function based on the [[Substitution-Permutation Network\|SP-Network]].
### Algorithm
- There is a key of 64-bit which is shortened to 56-bit key to generate Round Keys (as seen in [[Round Key Generation in DES\|Round Key Generation in DES]])
- The Round Keys are then used to perform the Encryption similar to [[Feistel Network\|Feistel Network]] Encryption with the [[Round Function of DES\|Round Function of DES]] as its Round Function.
	- The Input of 64-bits (8 blocks of 8-bits) is divided into 2 halves, one of the halves (let's say Right Half) is going to be put through the round function and [[XOR\|XOR]]ed with the Left Half.
	- Then the places are going to be flipped, Left Half goes to the Right and the original Right Half (untouched by the Round Function) goes to the Left side to be processed next round.
	- There are a total 16 rounds, so each half will go thorugh an effective 8 rounds of Encryption instead of 16.

### Analysis
- Pattern of the [[S-Boxes of DES\|S-Boxes of DES]] are fixed and the same S-Boxes are repeating for every round which means that the ***input pattern remains intact*** i.e., the pattern of bits remain the same in the plaintext and ciphertext since it is never challenged. This weakness was overlooked due to no one expecting inputs like all-zeroes or all-ones or a strange pattern of zeroes and ones.
- ***[[DES Master Key\|DES Master Key]] Length fell short*** for modern computing at just 64-bits
- ***Structural Weakness of Feistel Network***: The plaintext being broken from 64-bits to 32-bits & only working on one half at a time, meant instead of 16 rounds there are only 8 rounds of Encryption and hence we tend to be falling prey to the [[Overconfidence Effect\|Overconfidence Effect]] where we Overestimate the Cipher's capabilities.

---
# Footnotes