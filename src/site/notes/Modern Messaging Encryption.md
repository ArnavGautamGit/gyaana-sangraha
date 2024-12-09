---
{"dg-publish":true,"permalink":"/Modern Messaging Encryption/","tags":["CyberSec"]}
---


---
# Modern Messaging Encryption
> Messaging & how its encrypted in the Modern Day

First the message is hashed by a [[Hashing\|Hashing]] Algorithm like [[SHA-3\|SHA-3]].
Then the message and the hash is encrypted together in a fashion similar to the first few steps of [[Digital Signatures\|Digital Signatures]]:

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/digital-signatures/#a1" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



The concept of Digital Signatures uses [[Asymmetric Key Encryption\|Public Key Cryptography]] by [[Hashing\|Hashing]] the personal information of the sender on the sender side. The servers already store a hash of your account info for the login prcedure. The hash is then encrypted by the sender's Private Key. 

</div></div>


Then after this the entire message (with the encrypted hash) is encrypted by a [[Symmetric Key Encryption\|Symmetric Key Encryption]] and sent over.

The difference being that the instant messengers prefer not to use heavy algorithms like [[RSA (Rivest-Shamir-Adelman)\|RSA (Rivest-Shamir-Adelman)]] to make themselves "faster" even if it compromises (or seems to compromise) security.

Symmetric Key Encryption ensures [[Confidentiality\|Confidentiality]] and Speed.
Asymmetric/Public-Key Encryption ensures [[Authentication\|Authentication]].
Hashing is used to ensure [[Integrity\|Integrity]].

---
# Footnotes