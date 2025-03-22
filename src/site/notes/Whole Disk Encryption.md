---
{"dg-publish":true,"permalink":"/Whole Disk Encryption/","tags":["Academics","CyberSec"]}
---


---
# Whole Disk Encryption
> The Process of Encrypting the contents of the entire disk by the use of either [[Cryptographic Encryption Algorithms\|Logical Software-based Encryption]], Bit-by-bit Encryption or by using Hardware-level Encryption to prevent any unauthorised party from viewing, editing or deleting any data inside the specific disk. 

Hardware Level Encryption is considered the strongest and Software-based Encryption can be bypassed by using specific Hardware or the use of [[Exhaustive Key Search\|Brute-Force Key Search]] if the password is simple enough. 
Although for general ease-of-use, Software-based Encryption is considered sufficient. 

### Tools
BitLocker is a popular Disk Encryption tool for Windows & works by leaving an unencrypted partition of the drive to boot from but the entire Operating System is encrypted. Meaning that a person would need to know the password to gain entry. 

VeraCrypt is a good choice for cross-platform [[On-The-Fly Encryption (OTFE)\|On-The-Fly Encryption (OTFE)]] also called as "Transparent Encryption" where the encryption & decryption occurs automatically as you open and close files, given that you have already provided the key to access the files for the first time. 

---
# Footnotes