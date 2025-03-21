---
{"dg-publish":true,"permalink":"/Playfair Cipher/","tags":["CompSci","CyberSec"]}
---


---
# Playfair Cipher
Invented by Charles Wheatstone in 1854 and named on his friend - [[Lyon Playfair\|Lyon Playfair]] is one of the Polyalphabetic [[Substitution-based Ciphers\|Substitution-based Ciphers]] which uses [[Keyed Encryption\|Keyed Encryption]]. Since it encrypts more than one of the alphabets of the plaintext at the same time, it is also one of the first [[Block Ciphers\|Block Ciphers]] in the world (if not THE first).

- Uses $\large 5 \times 5$ matrix which uses a keyword as a [[Cryptographic Key\|Cryptographic Key]] (example: Monarchy)
- Each element of the matrix needs to be filled in a way to avoid repetition of letters.
- The Matrix will start with the keyword, Monarchy (or any other keyword)
- 1 pair of alphabets have to share the element since it is not possible to get a square matrix with 26 alphabets. The closest square is 25 (hence the matrix is also $5 \times 5$).
- We chose I and J to be such a pair since I occurs far more than J since J is one of the least frequently occuring alphabets in the English language. In this entire note, the previous sentence is the first occurence of a J. 
$$\begin{bmatrix}
M & O & N & A & R \\
C & H & Y & B & D \\
E & F & G & I/J & K \\
L & P & Q & S & T \\
U & V & W & X & Z \\
\end{bmatrix}
$$
---
### Rules for using the Playfair Cipher
- No repeating letters allowed in the matrix
- If letters are repeating in a particular digram in the plaintext, add an 'X' between the two repeating letters for the first occurence. X is also added if the plaintext is falling short of an alphabet to form a digram. Although, we check for repetitions first.
- Divide the plaintext into groups of 2 letters (called Digram)
- If the two alphabets in the digram occur in the same row, shift right and wrap-around. (if needed)
- If the two alphabets in the digram occur in the same coloumn, shift down and wrap-around. (if needed)
- If the two alphabets in the digram occur in the same rectangle, swap.

---
### Examples of Playfair Cipher's working
Let's say we were to take a random plaintext. Let's say the chosen word is HELLO.
***Given plaintext :*** H-E-L-L-O
Splitting into digrams it is: HE--LL--O
Now the two Ls are falling in the same digram.
Hence we add an X.

The CORRECT Digram is: HE--LX--LO

Now, write the Key Matrix: 
$$\begin{bmatrix}
M & O & N & A & R \\
(C & H) & Y & B & D \\
(E & F) & G & I/J & K \\
L & P & Q & S & T \\
U & V & W & X & Z \\
\end{bmatrix}$$
Now, check for positions of H and E in this matrix.
They are inside a small rectangle. which is replresented below:
$$\begin{bmatrix}
C & (H) \\
(E) & F \\
\end{bmatrix}
$$
H will be encrypted as C and F will be encrypted as E in this digram.
Repeat this process for every Digram in the plaintext to get Ciphertext.
Ciphertext for HELLO: "CFSUPM"

Remember, the repeating alphabets need to be in the same digram, there are words where that will not happen. ATTACK is one such word. AT and TA will be split to different digrams. In the same way there are multiple other such words.

---
### Weakness & Cryptanalysis
Unlike the [[Vigenère Cipher\|Vigenère Cipher]], this Cipher is not protected against digram-based [[Frequency Analysis\|Frequency Analysis]] and it still has the same problems as the previous iterations of Substitution Ciphers. Still, this is still an interesting creation for low level security - if secrecy is not of that paramount importance.

It is not easy to break the Cipher without computers.

---
# Footnotes