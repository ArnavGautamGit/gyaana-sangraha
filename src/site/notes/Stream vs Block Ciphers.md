---
{"dg-publish":true,"permalink":"/Stream vs Block Ciphers/","tags":["CompSci","CyberSec"]}
---


---
# Stream vs Block Ciphers
==***[[Stream Ciphers\|Stream Ciphers]]***==: A Cipher which directly converts one symbol of the plaintext to ciphertext. Most of the algos we have seen until now are Stream Ciphers.
==***[[Block Ciphers\|Block Ciphers]]***==: Translates multiple letters or words of the plaintext as a singular block of text. Similar to Columnar Transposition Cipher.

| STREAM CIPHERS                                                                  | BLOCK CIPHERS                                                                                                                                                   |
| ------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| No Buffer. i.e., Speed++                                                        | Slower speed                                                                                                                                                    |
| Lower Diffusion                                                                 | Made for Higher Diffusion                                                                                                                                       |
| Low Error Propagation                                                           | Error Propagation is possible                                                                                                                                   |
| Not immune to insertion of symbols i.e., vulnerable to modification/fabrication | Immune to fabrication and/or modification since a single character being added or removed doesn't affect the cipher much since it operates on groups of symbols |



---
# Footnotes