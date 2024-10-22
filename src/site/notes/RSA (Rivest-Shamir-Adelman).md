---
{"dg-publish":true,"permalink":"/RSA (Rivest-Shamir-Adelman)/","tags":["CyberSec"]}
---


---
# RSA (Rivest-Shamir-Adelman)
> An [[Asymmetric Key Encryption\|Asymmetric Key Encryption]] Algorithm developed by 3 experts whose last names are used to name the Algorithm. RSA stands for Rivest, Shamir and Aldeman - the last names of the inventors.

Although being Asymmetric means it is slower than [[Symmetric Key Encryption\|Symmetric Key Encryption]], but it offers a great feature other algorithms do not - its key size, which is theoretically infinitely scalable but it is currently commercially used at 4096 bits in length.

### Algorithmic Basis
Our Class Slides also mention that it was "based on exponentiation in a finite [[Galois Field\|Galois Field]] over integers modulo a prime". God knows what all that jargon means.
It is also said to be influenced by the mathematical concepts used in [[Diffie-Hellman Key Exchange\|Diffie-Hellman Key Exchange]] - according to Professor Himashu Aggrawal.

### Foundational Concepts Required
The Algorithm's nature is completely mathematic - hence we would need to know certain mathematical concepts like: 
- [[Prime Numbers\|Prime Numbers]]
- [[Co-Prime Numbers\|Co-Prime Numbers]]
- [[Euler's Totient\|Euler's Totient]]
- [[Modulo (Mathematical Function)\|Modulo (Mathematical Function)]]
	- [[Calculate Modulo on Simpler Calculators\|Calculate Modulo on Simpler Calculators]]
	- [[Calculate Modular Inverse on Calculators\|Calculate Modular Inverse on Calculators]]

### Working
- We begin with two very large prime numbers $\large p$ & $\large q$. {[[RSA (Rivest-Shamir-Adelman)#^1\|#^1]]} 
- The prime numbers must be chosen in a way that on multiplication they give a big value. {[[RSA (Rivest-Shamir-Adelman)#^2\|#^2]]}
- Multiply $\large p$ & $\large q$ to get the number, $\large n$ {[[RSA (Rivest-Shamir-Adelman)#^3\|#^3]]}
- Apply [[Euler's Totient\|Euler's Totient]] (for any prime number, its is the prime number - 1) i.e., $$\Large m=\phi_n = (p-1)\cdot(q-1)$$
- Now choose a smaller number, $\large e$ which is coprime with $\Large \phi_n$.
- Now we find a number $\large d$ such that: multiplication of $\large d$ & $\large e$ modulo $\large m$ must be 1. $$\Large (d \cdot e) \ mod \ m  = 1$$
-  $\large e$ & $\large n$ are Public Keys
-  $\large d$ is the Private Keys
- To encrypt the message & obtain Ciphertext: $$\Large Ciphertext = m^{e} \ mod \ n$$
- To Decrypt the message & obtain Plaintext: $$\Large Plaintext = {(Ciphertext)}^{d} \ mod \ n$$


---
# Footnotes
1. Since the RSA uses Large and Very Large Prime numbers, it is important to use the concept of [[Primality Testing\|Primality Testing]].
{ #1}

2. Prime Numbers are preferred since they have no factors apart from 1 and the number itself. So that makes any MEANINGFUL factorisation impossible since using 1 is not helpful and the person cannot use the Prime Number itself since the number itself is what cryptanalysts are trying to find.
{ #2}

3. $\large n$ is intenionally kept so large (by using large Prime Numbers $\large p$ and $\large q$) so that [[Prime Factorisation\|Prime Factorisation]] (finding prime factors $\large p$ and $\large q$ when $\large n$ is known) becomes computationally impossible to find in given session length.
{ #3}

4. 