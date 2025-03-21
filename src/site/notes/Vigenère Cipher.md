---
{"dg-publish":true,"permalink":"/Vigenère Cipher/","tags":["CompSci","CyberSec","History"]}
---


---
# Vigenère Cipher
It is an improvement of the [[Ceaser Cipher\|Ceaser Cipher]] and the Wikipedia Article calls this cipher a "type" of the Ceaser Cipher. It was given by [[Giovian Battista Bellaso\|Giovian Battista Bellaso]] in 1553 and was miscredited to [[Blaise de Vigenère\|Blaise de Vigenère]] since he gave the [[Autokey Cipher\|Autokey Cipher]] in 1586 which ended up being more popular & the first book describing general method of cryptanalysis of table-based ciphers written by [[Friedrich Kasiski\|Friedrich Kasiski]] in 1863 later clubbed all these ciphers and placed them in the category of "Vigenère Ciphers" - creating this confusion. The Cipher was unbreakable for 310 years until the publishing of Kasiski's book in 1863.

It is popularly called *"le chiffrage indéchiffrable"* (i.e., *"the indecipherable cipher"*) in French.

### Method of Encryption
It uses a [[Keyed Encryption\|Keyed Encryption]] method with a [[Cryptographic Key\|Cryptographic Key]] which comprises of a phrase or word. The Cipher replaces the $\large i^{th}$ alphabet of the plaintext with the position of occurance of the $\large i^{th}$ alphabet of the key in the language - including wrap around if needed.

It works best if the number of alphabets in the key is the same as the number of alphabets in the message. For larger messages, [[The Running Key Cipher\|The Running Key Cipher]] variant of this Cipher allows for the use of passages from a large text such as a book. Since it replaces each alphabet individually, it is also one of the best examples of the working of [[Stream Ciphers\|Stream Ciphers]].

It is a simple [[Substitution-based Ciphers\|Polyalphabetic, Substitution-based Cipher]] since a particular alphabet in plaintext could result in a different alphabet in ciphertext in each occurance, i.e., unlike the Ceaser Cipher, A will not always be encrypted as D, it may be encrypted as D once and then later in the message, A may be encrypted as G. 

### Working Example
if the plaintext is `attacking tonight` and the key is `OCULORHINOLARINGOLOGY`, then:

- the first letter `a` of the plaintext is shifted by 14 positions in the alphabet (because the first letter `O` of the key is the 14th letter of the alphabet, counting from zero), yielding `o`;
- the second letter `t` is shifted by 2 (because the second letter `C` of the key means 2) yielding `v`;
- the third letter `t` is shifted by 20 (`U`) yielding `n`, with wrap-around;

and so on; yielding the message `ovnlqbpvt hznzouz`. If the recipient of the message knows the key, they can recover the plaintext by reversing this process.

### Weakness
Although this Cipher is free from [[Frequency Analysis\|Frequency Analysis]], but the key on this Cipher repeats and the letters in the key re directly substituted. Improvement on this aspect of the Cipher led to the [[Vernum Cipher\|Vernum Cipher]] which has an infinite key length and [[XOR\|XOR]]s the key and plaintext to form ciphertext. Addressing both the shortcomings.

One can easily recognise the Cipher by using the [[Kasiski's Examination\|Kasiski's Examination]] which basically checks if there is a repetition in the Ciphertext and the [[Friedman's Test\|Friedman's Test]] can be used to find the Keylength using a specific Formula taking into account the Probabilities of a random alphabet repeating in the same text, among other things. Check the Wikipedia page of this Cipher and scroll to Cryptanalysis section.

After we figure out the Keylength, the Ciphertext can be written in columns with each column representing a singular character of the Key.
Now we decrypt each column using the same method we used for [[Ceaser Cipher#Cryptanalysis\|Ceaser Cipher#Cryptanalysis]]. The Ceaser Cipher Key is the letter of the Key of the Vigenère Cipher.

---
# Footnotes