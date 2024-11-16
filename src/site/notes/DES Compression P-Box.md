---
{"dg-publish":true,"permalink":"/DES Compression P-Box/","tags":["Academics","CyberSec"]}
---


---
# DES Compression P-Box
> A [[Compression P-Box\|Compression P-Box]] used in the [[Round Key Generation in DES\|Round Key Generation in DES]].

It is not used in anything else - not that I know of any other place in the algorithm such Compression Boxes are used.

### Working
During [[Round Key Generation in DES\|Round Key Generation in DES]], After the Parity Drop & division of the 56-bit Key into two 28-bit halves:

When the two 28-bit Binary Keys are put into the DES Compression Box, we know they have 4 blocks of 7-bits each which should combine and make 8 blocks of 7-bits (56-bits again) but the Compression P-Box would actually be missing a few coordinates, so certain Binaries will point to Rows and Columns that do not exist & hence will be dropped. ([[DES Compression P-Box#^1\|#^1]])

We will be left with 8 blocks of 6-bits each which form the [[DES Round Keys\|DES Round Keys]].

---
# Footnotes
1. This process of Binaries pointing to Rows and Columns were also seen in the [[Round Function of DES\|Round Function of DES]].
{ #1}

2. 