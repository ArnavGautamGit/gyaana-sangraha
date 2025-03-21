---
{"dg-publish":true,"permalink":"/Ceaser Cipher/","tags":["Academics","CyberSec","Military","History"]}
---


---
# Ceaser Cipher
It is a [[Cipher\|Cipher]] of the [[Shift Encryption Class\|Shift Encryption Class]] made by [[Julius Ceaser\|Julius Ceaser]] for Military & Espionage use on the field sometime during his life for the use in Ancient Roman Empire. It is considered the FIRST cipher operating on written material in Europe. The Cipher is one of the simplest mono-alphabetic [[Substitution-based Ciphers\|Substitution-based]] [[Stream Ciphers\|Stream Ciphers]].

This Cipher uses a very simple Encryption Method. We just shift the alphabets ahead by $\large n$ $\large (\forall$ $\large{n} \in N)$.
$$\LARGE C_i = P_i+n$$
Here, $\large C_i$ refers to the $\large i^{th}$ letter of resulting ciphertext whereas $\large P_i$ refers to the  $\large i^{th}$ letter of the plaintext that needs to be ciphered.

For Example: We know Ceasar used the shift of 3 i.e., $\large n =$ 3, then:

| ***Plaintext***  | H   | E   | L   | L   | O   |
| ---------------- | --- | --- | --- | --- | --- |
| ***Ciphertext*** | K   | H   | O   | O   | R   |

In Caesar's time... in the Eurpean Civilization, only a few knew how to read! So written text was ciphered already. Add to it simple algorithm that doesn't need to be written down and is as easy to explain as it is... genius!

---
### Cryptanalysis
Its Cryptanalysis is fairly easy using [[Exhaustive Key Search\|Exhaustive Key Search]] and figure out the number of letters a particular alphabet has undergone. We replicate that on the entire message until it makes sense.

Two main weaknesses:
1. Keyspace is too small
2. Substitution is too predictable

Which is why we moved away from the [[Shift Encryption Class\|Shift Encryption Class]] and into better classes of [[Substitution-based Ciphers\|Substitution-based Ciphers]] like Mono-alphabetic Ciphering.

---
# Footnotes