---
{"dg-publish":true,"permalink":"/RC4 Encryption/","tags":["CompSci","CyberSec"]}
---


---
# RC4 Encryption
> Recent one of the [[Stream Ciphers\|Stream Ciphers]] which was inspired by the [[Vernum Cipher\|Vernum Cipher]] and became popular for real-time encryption of 1 unit data at a time (such as encrypting the phone calls of leaders of state).

The Algorithm was later improved upon and made into the [[RC5 Encryption\|RC5 Encryption]]

### RC4 vs other (Modern) Block Ciphers
- It was a much faster algorithm and worked much better with a smaller plaintext.
- Unlike Block Ciphers, RC4 needs to be synchronus, the keystream and data stream needs to be synchronus for the key to work & the decryption to be effective. Otherwise data would not decrypt & the algorithm would backfire.

### Working
- The sender and receiver share a Master Key.
- Master Key generates a Key Stream.
- Key Stream needs to be in-sync between both parties at all times.
- Unlike the [[Vernum Cipher\|Vernum Cipher]], the key does not need to be infinite and key can repeat.
- Plaintext is [[XOR\|XOR]]ed with Key to encrypt & Ciphertext is XORed with Key to decrypt as explained in: [[Relevance of XOR in Cryptography\|Relevance of XOR in Cryptography]] 

#### Caveats
- ==***Randomness***==: Are the keys generated truly random? It seems moronically oxymoronic to use an ***algorithm*** to generate a ***random*** keystream which is also ***deterministic*** (so the other party can do the same to decrypt).
	- The maximum we can do is generate a pseudo-random keystream - which produces the keystream which seems random unless you know the algorithm.
	- There will be no pattern in the keystream if the Master Key is long

---
# Footnotes