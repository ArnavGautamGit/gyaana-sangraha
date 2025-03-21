---
{"dg-publish":true,"permalink":"/Asymmetric Key Encryption/","tags":["Academics","CyberSec"]}
---


---
# Asymmetric Key Encryption
> Specially made [[Keyed Encryption\|Keyed Encryption]] Algorithm that involve two unique keys - a Private Key and a Public Key. Only one of the keys can be used to encrypt at a time and the other would need to be used for decryption i.e., same key cannot encrypt and decrypt the data on both ends - Keys are Asymmetric.

In the conventional case (although this is not a hard & fast rule), the user would freely distribute the Public Key so that other users could encrypt messages & send it to them while the only key that can decrypt them would be their secret Private Key which is unique and only they have access to it. Such a system can only grant [[Confidentiality\|Confidentiality]] and can never grant [[Authentication\|Authentication]] since the message is encrypted but we can never be sure whether the Identity of the sender is being spoofed or not..

To get Authentication, flip this key relation to provide Authentication (without Confidentiality). One uses their Private Key to encrypt. Since the sender's Private Key is unique to them, it makes it known to the receiver about the authenticated identity of the sender of the message.

Old System for achieveing both [[Confidentiality\|Confidentiality]] and [[Authentication\|Authentication]]:
To get both, it is best to use first your own Private Key & then the authorised receiver's Public Key to encrypt. The message can only be unlocked by the Receiver's Private Key.
Nowadays we use [[Modern Messaging Encryption\|Modern Messaging Encryption]]

In Modern Cryptography, it is considered that [[RSA (Rivest-Shamir-Adelman)\|RSA (Rivest-Shamir-Adelman)]] is a good example of Asymmetric Key Encryption.

---
# Footnotes