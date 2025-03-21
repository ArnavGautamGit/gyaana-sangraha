---
{"dg-publish":true,"permalink":"/Substitution-based Ciphers/","tags":["CompSci","CyberSec"]}
---


---
# Substitution-based Ciphers
> In Cryptography, a *Substitution Cipher* is a method of encrypting in which units of plaintext are replaced with the ciphertext, in a defined manner, with the help of a key; the "units" may be single letters (the most common), pairs of letters, triplets of letters, mixtures of the above, and so forth. The receiver deciphers the text by performing the inverse substitution process to extract the original message.

Depending upon the number of characters being substituted, there are 2 kinds of Substitution Ciphers:
1. ***==Mono-alphabetic==*** - a particular alphabet in plaintext will always be encrypted as the same alphabet in ciphertext i.e., A is always substituted by D in [[Ceaser Cipher\|Ceaser Cipher]].
2. ***==Polyalphabetic==*** - a particular alphabet in plaintext should result in a different alphabet in ciphertext in each occurance i.e., A being substituted as some other letter which may or may not be the same (depends on the key) in [[Vigenère Cipher\|Vigenère Cipher]] and depends on the di-gram distribution in [[Playfair Cipher\|Playfair Cipher]].

One of the earliest of these Substitutions belong to the [[Shift Encryption Class\|Shift Encryption Class]] - where the substitution was made due to shifting of letters K distance along the alphabet. A pioneer in this vision was [[Julius Ceaser\|Julius Ceaser]] with his [[Ceaser Cipher\|Ceaser Cipher]].

From the results of its cryptanalysis took birth the many mono-alphabetic substitution Ciphers, since it was realised that shifting was predictable and we needed Ciphers where the substitution does not occur in such easy way.

Mono-alphabetic Ciphers had key space of $\large26!$ and were broken finally by using [[Frequency Analysis\|Frequency Analysis]]: the letter E appears the most followed by T while the letter J appears the least in the English Language.

To combat this problem of frequency Analysis, [[Vigenère Cipher\|Vigenère Cipher]] was developed to make the frequencies of individual letters and alphabets homogenous across languages. It was only broken in 1863 and once, Computers got personal use in 1975, then we got [[Modern Cryptographic Ciphers\|Modern Cryptographic Ciphers]] based on these very principles.

---
# Footnotes