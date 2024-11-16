---
{"dg-publish":true,"permalink":"/Exhaustive Key Search/","tags":["CyberSec"]}
---


---
# Exhaustive Key Search
> A [[Cryptanalysis\|Cryptanalysis]] Technique to find the key & decrypt a ciphertext given that we have the cipheertext and we know which of the [[Cryptographic Encryption Algorithms\|Cryptographic Encryption Algorithms]] has been used to excrypt.

This is ***also called as "Brute Force Search"*** since we are trying to brute force our way through the system by trying a random key to decrypt the algorithm & we store it as a candidate key if the plaintext makes sense. If it is confirmed that the generated plaintext is the actual plaintext then the Candidate Key is the True Key we were looking for and Cryptanalysis is successful.
If the plaintext does not make sense, we keep trying new random keys until one of them works.

---
# Footnotes