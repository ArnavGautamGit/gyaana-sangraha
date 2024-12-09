---
{"dg-publish":true,"permalink":"/Digital Signatures/","tags":["Academics","CyberSec"]}
---


---
# Digital Signatures
> Digital Equivalent of Paper Signatures that are unique to specific user. Since on the Internet, it is assumed that each user has (or is identified by) 1 account - these signatures are unique for each account.

Just like Paper Signatures, the purpose is still to ensure [[Authentication\|Authentication]] and avoid Identity Theft.

The concept of Digital Signatures uses [[Asymmetric Key Encryption\|Public Key Cryptography]] by [[Hashing\|Hashing]] the personal information of the sender on the sender side. The servers already store a hash of your account info for the login prcedure. The hash is then encrypted by the sender's Private Key.
{ #a1}


The Full message (including the encrypted hash) is then encrypted again using their own Private Key by a trusted third-party Digital Signature Certification Authority that stores this information in the form of Digital Certificates.

Multiple such Digital Certificates are stored by the Authority on Directories where you need the Public Key of the Authority storing the certificate. If your certificate is stored by another authority then authorities always have Cross-Verified each other i.e., you can find the Public key of another authority in the directories maintained by your own and scan the other authority's directories to fetch the receiver's public key.


---
# Footnotes