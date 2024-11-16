---
{"dg-publish":true,"permalink":"/Frequency Analysis/","tags":["Academics","CyberSec"]}
---


---
# Frequency Analysis
In [[Cryptanalysis\|Cryptanalysis]], the term is defined as:
> The process of using frequency of occurence of each letter of the alphabet of a language to map the most and least used letters in the language for application in breaking any codes to transmit information from one person to the next.

We take Dictionaries around the world and books written, assess them to see which letters appear and how many times, finding the ratio of how many times a particular alphabet appeared with respect to the total number of alphabets gives us a value between 0 and 1. Calculated for each letter in various languages, we knowwhich of the letters appear more than the others.

This process can be perfomed for di-grams (pair of alphabets) and tri-grams (triplet of alphabets) and even full words!

---
### Usecase and Example
In English, the letter E repeats the most and the word "the" repeats the most... using this, Any Interceptor simply needs to write down the frequencies of repetition in the message and they shall see the highest frequency match E, the second highest match T and if they have these two words, they can piece together the words "the" and find the code for H. They can crack the words like - *he, she, the, thee, them, these* and eventually crack the encryption pattern and decode all the future communication until the pattern is changed. 

---
# Footnotes