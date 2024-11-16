---
{"dg-publish":true,"permalink":"/Digital Signatures/","tags":["Academics","CyberSec"]}
---


---
# Digital Signatures
> Digital Equivalent of Paper Signatures that are unique to specific user. Since on the Internet, it is assumed that each user has (or is identified by) 1 account - these signatures are unique for each account.

Just like Paper Signatures, the purpose is still to ensure Authentication and avoid Identity Theft.

The concept of Digital Signatures uses [[Asymmetric Key Encryption\|Public Key Cryptography]] by [[Hashing\|Hashing]] the personal information of the sender on the sender side. The servers already store a hash of your account info for the login prcedure. The hash is then encrypted first by the sender's Private Key & then by the receiver's Public Key (so that only receiver can decrypt it with their singular Private Key).

The entire message along with the encrypted hash is encrypted using a Secure [[Symmetric Key Encryption\|Symmetric Key Encryption]] & sent over.

---
# Footnotes