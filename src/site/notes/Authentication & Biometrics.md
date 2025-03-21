---
{"dg-publish":true,"permalink":"/Authentication & Biometrics/","tags":["Academics","CyberSec"]}
---

###### Created on: 29/09/2023
###### Last updated: 29/09/2023

----
# Index/Contents
[[Authentication & Biometrics#1. What is Authentication?\|#1. What is Authentication?]]
[[Authentication & Biometrics#2. What are Biometrics?\|#2. What are Biometrics?]]
[[Authentication & Biometrics#3. What is Multifactor Authentication?\|#3. What is Multifactor Authentication?]]
[[Authentication & Biometrics#4. General Rules for strong Passwords\|#4. General Rules for strong Passwords]]
[[Authentication & Biometrics#Reference Material\|#Reference Material]]

-----
# 1. What is Authentication?
*Authentication* means verifying if the data or information that is known is correct or not.
In Computing terms, *Authentication* is the process of confirming whether the user is who they are claiming to be. 
Example: I cannot use Charu ma'am's account unless I know her password. A password is a form of authentication.
## 1.1 Authentication Mechanisms 
There are mainly 3 types of Authentication mechanisms that we study in the syllabus:
1. Passwords/PIN (pretty self-explanatory)
2. ==***Tokens***==
3. ==***Biometrics***==
### 1.1.1 Authentication using Passwords
A password is (in the simplest definition possible) a mutually agreed-upon code word used - assumed to be known only to the system and the user. Some cases system assigns the user their password (like recovery passwords on Crypto Wallets) 
Passwords are the most vulnerable type of authentication tool/mechanism in computing today $^{[1]}$
Passwords suffer from the following cons:
1. ==***Loss***==: Passwords lost cannot be traced. New ones need to be assigned.
2. ==***Use***==: Needing to use a password for each access is inconvenient and time-consuming
3. ==***Disclosure***==: IF the password is disclosed to unauthorised people, the file is now vulnerable. Password must be changed and everyone in the organisation needs to be given a new password.
4. ==***Revocation***==: To revoke someone's access, we need to change the password and the rest of the organisation needs to be told of the new password (preferably on a platform where the revoked user is not present)

Why are passwords not considered safe?
To fish out a password, you need the following:
1. Try all possible passwords
2. Try all frequent passwords
3. Search for a system list of passwords
4. Ask the user directly.

However, the passwords can also be fished out unethically:
1. Brute Force Attack
2. Interrogation of the user
3. Blackmail of the user
4. Keylogger attack etc etc
#### 1.1.1(A) How does a Brute Force Attack on a password work?
Generally, Passwords need to be a minimum of 8 characters. Interestingly, only assuming that a user is allowed to use only the 26 English alphabets on the site, (neither special characters nor numeric values) there are already 1 Trillion or $\large 10^{12}$ possible passwords. Seems secure?
If a computer tries to input one password every milisecond, it will take 150 years. Make the computer speed to 1 password tried per microsecond, it takes 2 months. Still feels secure?
Consider this, the hacker has to go through only half that number if we spread all possible passwords evenly across a graph. Since passwords are needed to be memorised, the passwords are simpler, hence not near 0.5 on the graph, but closer to 0.2 or 0.3...
Assuming it is 0.3 it will only take 0.18 months (i.e., 5.4 days) to crack.

This becomes faster if the attacker knows your name and/or birthday (which people often include in their passwords). It can be done in less than 1 day
### 1.1.2 Authentication using Tokens
Tokens are another way of authenticating users. They can be classified in two ways:
1. On the basis of Activity
2. On the basis of State
#### 1.1.2.1 Types of Tokens based on Activity

| Active | Passive |
|---|---|
| Action needed from user to authenticate | No action needed |
| Need to be read by a sensor | Works without electronic sensors |
| Examples: Metro Card, Debit/Credit Card | Example: Aadhar, PAN or other Photo ID |
#### 1.1.2.2 Types of Tokens based on State

| Static | Dynamic |
|----|----|
| Only useful for On-site Authentication | Remote-Authentication option available |
| No change in internal state | Internal state changes as some computations occur |
| Generally have no computing power | Has Computing Power |

It is safe to say that Passive Tokens are Static, and Active tokens are Dynamic. Converse is also true.

---
# 2. What are Biometrics?
Password/Authentication Metrics that use unique Biology of a human that differentiates them from other humans. Examples: Hand Geometry, Finger Print, Retinia and Iris scans, voice and face recognition et cetera.
Following notes are all hand-written from class.
## 2.1 Problems with Biometrics
1. Biometrics are relatively new and some people have problems accepting due to privacy and  Biometric Authentication's asssociation with criminal investigation.
2. Biometric devices are costly to put up for every employee in a big organisation no matter if the costs come down by large volume of supply and widespread acceptance. Since passwords are simple piece of code and much easier to implement cost wise.
3. Readers and comparison is a single point of failure. If you can beat it or circumvent it, then the entire system is open to you. If it fails, there is no other way to login because if there is another way, then that is stupid - because then your system is not using any positives that Biometrics bring if you are still using primitive methods!
4. Reduced accuracy inu variance. Since variance has to be provided to compensate for uneven spread of hand/finger pressure or changes in voice that can be caused due to infection (these can also give false negatives).
5. False Positives and False Negatives are possible and are undesirable due to a balance of variance and inconvenience (caused by reattempts of authorised users getting rejected due to humane factors stated in above point).
## 2.2 How to assess if a particular Biometric is better than another?
There are many metrics of assessment of biometrics. Some of them (in our syllabus) include Specificity, Sensitivity and Accuracy
There are some Variables one should remember first.
***A = True Positives*** (*Authorised user access granted*)
***B = False Positives*** (*Unauthorised user access granted*)
***C = False Negatives*** (*Authorised user access denied*)
***D = True Negatives*** (*Unauthorised User access denied*)
### 2.2.1 Sensitivity
Measures the degree to which the screen selects those whose names match with the person sought.
Ratio of true positive results to all authorised user results.
Calculated using the formula: $\dfrac{A}{A+C}$
### 2.2.2 Specificity
Measures the proportion of negative results among all people who are not sought
Calculated by the following formula: $\dfrac{D}{B+D}$
### 2.2.3 Accuracy
Measures the degree to which the test or screen correctly flags the condition or situation. Ratio of True readings to all readings.
Calculated using the formula: $\dfrac{A+D}{A+B+C+D}$

*Some Syllabus has been skipped* $^{[2]}$

---
Next Chapter ---> [[Computer Networks\|Computer Networks]]
# Reference Material
$^{[1]}$ Chapter 4, Section 4.5 of the book, "Security in Computing" - Charles P. Pfleeger, Shari Lawrence Pfleeger (J128 LRC Rack 5.8, Book 5813) 

$^{[2]}$ Dated 29th September 2023, *Ma'am said no need to study the ROC curve* when teaching this unit in the class.

