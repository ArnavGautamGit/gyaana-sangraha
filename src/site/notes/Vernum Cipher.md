---
{"dg-publish":true,"permalink":"/Vernum Cipher/","tags":["CompSci","CyberSec","Military","History"]}
---


---
# Vernum Cipher
> It is one of the best [[Stream Ciphers\|Stream Ciphers]] of the early 20th Century [[Keyed Encryption\|Keyed Encryption]] Ciphers which was made on the pre-requisite that the size of the [[Cryptographic Key\|Cryptographic Key]] is infinite & equal to the number of characters in the message.

This Cipher was used on field during [[The U.S-Soviet Cold War\|The U.S-Soviet Cold War]] by spies using continous passages from books and book series as a continous, near-infinte keys written on tear-away notepads where both parties would have a copy of the notepad and send a message and discard the page/number of characters in the key that were already used (which was already discussed). This usecase got the Cipher a new name - "One-Time-Pad".

#### Why was it not widely used?
- The ***Infinite Key Size*** was not possible & the approach makes even "Near-Infinite" Key Size unsustainable since it would need maintainers who would need to keep adding to the key. More People communicate than the ones adding to the keys.
- ***Key should also not repeat*** or have a discernable ***pattern***.
- Infinite Key that doesn't repeat? Not possible unless you use the text from all the books and Wikipedia directly - even then words would repeat - so still cannot be used as-it-is.

Despite this, it inspired the creation of the [[RC4 Encryption\|RC4 Encryption]]

#### Working
The Plaintext would be [[XOR\|XOR]]ed with the Key (Infinite Key) & generate an encrypted output. You may need to convert your input into Binary. See Also: [[Relevance of XOR in Cryptography\|Relevance of XOR in Cryptography]]

---
# Footnotes