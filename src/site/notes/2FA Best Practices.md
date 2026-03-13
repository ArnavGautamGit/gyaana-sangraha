---
{"dg-publish":true,"permalink":"/2FA Best Practices/"}
---


---
# 2FA Best Practices
> Some things on how to handle account security for all your accounts using 2FA or [[Multi-Factor Authentication\|MFA]] in general. This notes lists those things. (This will keep being updated)

When using 2FA there are some things one must keep in mind, and this note lists those details. One of the main points is to not use Authenticator Apps since they are not full-proof against [[Phishing\|Phishing]] due to not being able to verify website links unlike Physical Security Keys. Even if you decide to use Authenticator Apps, I have used the best practices for them too. 

### Keep a minimum of 2 Security Keys (if using physical keys)
Some accounts like Apple make sure that you cannot add just 1 key, you need to have a minimum of 2 keys to start the process of Authentication since you need a primary and backup key.

### Keep a backup of secret code (if using App-based 2FA)
If you are using an Authenticator App, keep in mind that you might need to switch apps if there is a discovery/revelation that it has a vulnerability or it is shutting down due to lack of users/funds. 
It is best to keep the Secret Codes or its QR form or both in print where you store your birth ceritficiate and similar government documents. It is best to make an account on PC & just pressing Ctrl+P (or Cmd+P on Mac) to immediately take a printout instead of saving the PDF (in-case a hacker might get access to files on your PC via [[Ransomware\|Ransomware]])

### Avoid SMS-based verification as much as possible
While some services like Google and Apple have their proprietary ways of authenticating users which does not use SMS even if you do not use any other methods listed above, it is important that many Govt Websites such as UIDAI and DigiLocker in India use SMS for verification due to its reach. 
Nowadays I think people should be given the OPTION to at least use Authenticator Apps on govt sites and databases (if not also physical keys). Due to SMS being unencrypted plain-text and SIMs being vulnerable to [[SIM Swapping\|SIM Swapping]] and [[SIM Cloning\|SIM Cloning]] Attacks, it is best to avoid using SMS for 2FA unless it is the only option left.

---
# Footnotes