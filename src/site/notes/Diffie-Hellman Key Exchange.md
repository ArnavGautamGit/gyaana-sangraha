---
{"dg-publish":true,"permalink":"/Diffie-Hellman Key Exchange/","tags":["CompSci","CyberSec"]}
---


---
# Diffie-Hellman Key Exchange
> A Technique for the exchange of Symmetric Keys using public parameters known to everyone. Never used much in practice due to the potential of it being easy to break for well-funded attackers, but it laid an impressive foundation for the development of [[Elliptical Curve Cryptosystems(ECC)\|ECC]], [[RSA (Rivest-Shamir-Adelman)\|RSA]] & [[ElGamal Encryption\|ElGamal Encryption]].

Diffie-Hellman Key Exchange was the first of its kind which proposed how both sender and receiver could receive a key without problems.

### Working Principles
- Both sides first agree on [[Global Parameters\|Global Parameters]] which are visible and can be seen by the entire world. 
- The Global Parameters include:
	- [[Prime Numbers\|Prime Number]] $\large q$. 
	- Its [[Primitive Root\|Primitive Root]] $\large \alpha$.
- Both sides (say A and B) take a number $\large X_A$ and $\large X_B$ respecitvely as [[Private Parameters\|Private Parameters]] with the restriction that both these numbers must be $\large\lt q$
- These Private Parameters are used to operate on Global Parameters to calculate the keys which are going to be symmetric on both sides using the power of Mathematics.

### Formulae used
A computes $\large Y_A$ $$\Large Y_A = \alpha^{X_A} \ mod \ q$$
B Computes for $\large Y_B$ $$\Large Y_B = \alpha^{X_B} \ mod \ q$$
The values of both are exchanged among one another.
Let the key used to encrypt the conversation between A and B be called as $\large K_{AB}$

A calculates the key using $\large Y_A$ they have and $\large X_B$ received from B: $$\Large K_{AB} = {(Y_A)}^{X_B} \ mod \ q$$
B calculates the key using $\large Y_B$ they have and $\large X_A$ received from A: $$\Large K_{AB} = {(Y_B)}^{X_A} \ mod \ q$$
Also note:
$$\Large K_AB = \alpha^{Y_A \cdot Y_B}$$

---
# Footnotes