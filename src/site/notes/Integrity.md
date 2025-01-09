---
{"dg-publish":true,"permalink":"/Integrity/","tags":["CyberSec","Academics"]}
---


---
# Integrity
> The Ability to maintain the state of any data in the system as long as an authorised party does not change it. ([[Integrity#^1\|#^1]])

Integrity is ensured by maintaining the trustwothiness of information resources.
Integrity requires that:
- the data stored in the system is correct, valid & kept updated.
- the data has not been changed without [[Authorisation\|Authorisation]] of an authorised party.

Message Integrity and Entity Integrity are maintained by two different methods:
1. For Messages, we use: [[Message Hashing\|Message Hashing]]
2. For Entities or Users, we use: [[Asymmetric Key Encryption\|Public Key Cryptography]] or [[Digital Signatures\|Digital Signatures]] in case of websites

Additionally, we know that Digital Signatures cannot be faked easily, but the messages can still be changed if an older or compromised encryption algorithm is being used, the hashes & checksums will be compared on both sides & if the message has changed in target, it will fail the check, both users will be notified (at least receiver will be) and the message will be discarded.

Attacks on Integrity: [[Man-in-the-Middle Attack\|Man-in-the-Middle Attack]]

---
# Footnotes
1. *'data'* contains both the personal details of the conversing parties and the messages exchanged, Integrity of both the message and the parties/entities must be protected.
{ #1}
