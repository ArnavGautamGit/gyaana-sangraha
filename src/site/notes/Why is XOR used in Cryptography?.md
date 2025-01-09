---
{"dg-publish":true,"permalink":"/Why is XOR used in Cryptography?/","tags":["CyberSec","Academics"]}
---


---
# Why is XOR used in Cryptography?
[[XOR\|XOR]] ($\large \oplus$) allows the sender to encrypt and the receiver to decrypt without much thought. Just XOR the two things you have & you get the one thing you need.
$$\large Plaintext \ \oplus \ Key = Ciphertext $$
$$\large Ciphertext \ \oplus \ Key = Plaintext $$
Because the Truth Table of XOR [[Logic Gates\|Logic Gate]] is such that there is a 50-50 chance of the output being 1 or 0, it gets extremely hard for the Cryptanalyst to figure out the order of input bits. This effect makes it harder to predict the plaintext & break the Encryption.

Use of [[Digital Logic\|Digital Logic]] in Cryptography was popularised by popularity of XOR-based algorithms such as [[RC4 Encryption\|RC4 Encryption]] and the unbreakable [[Vernum Cipher\|Vernum Cipher]].

---
# Footnotes