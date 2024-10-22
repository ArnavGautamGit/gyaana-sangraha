---
{"dg-publish":true,"permalink":"/Modern Cryptographic Ciphers/","tags":["CompSci","CyberSec"]}
---


---
# Modern Cryptographic Ciphers
When we realised that [[Product Ciphers\|Product Ciphers]] are better than [[Substitution-based Ciphers\|Substitution-based Ciphers]] and [[Transposition-based Ciphers\|Transposition-based Ciphers]], since catching substitution or transposition is easy if either is done alone. If both are done one after the other, then it is almost impossible to catch it. This advancement in Product Ciphering marked the transition into Modern Cryptographic Ciphers.

It is mathematically proven that:
1. Doing one of the two processes (Substitution or Transposition) before the other is mathematically better
2. After an 'n' number of substitutions and transpositions, the probability to avoid [[Cryptanalysis\|cryptanalysts]] breaking the cipher does not improve but has chances of worsening i.e., the cipher is more likely to get worse than get better after 'n' number of substitutions and transposition.
3. The value of 'n' changes depending upon algorithm used and message size among other things.

The strong presence of maths is also the reason why many [[Cryptography\|cryptographers]] and [[Cryptology\|cryptologers]] since the 20th Century often have close ties with Mathematicians or are Mathematicians themselves (like [[Claude Shannon\|Claude Shannon]]).

The Syllabus has the following Ciphers:
1. [[AES (Advanced Encryption Standard)\|AES (Advanced Encryption Standard)]]
2. [[RSA (Rivest-Shamir-Adelman)\|RSA (Rivest-Shamir-Adelman)]]
3. [[DES (Data Encryption Standard)\|DES (Data Encryption Standard)]]
4. [[RC4 Encryption\|RC4 Encryption]]
5. [[RC5 Encryption\|RC5 Encryption]]

See Also:
[[Criteriae for Good Cryptographic Algorithms\|Criteriae for Good Cryptographic Algorithms]]

---
# Footnotes
