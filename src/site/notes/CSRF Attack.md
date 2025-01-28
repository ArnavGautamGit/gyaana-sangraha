---
{"dg-publish":true,"permalink":"/CSRF Attack/","tags":["Academics","CyberSec","EthHack"]}
---


---
# Cross-Site Request Forgery (CSRF) Attack
> An attack which involves duping an end user into performing unwanted tasks on a website they are currently logged/authenticated in.

With the help of [[Social Engineering\|Social Engineering]] and [[Phishing\|Phishing]], one can easily make the user perform actions of the attacker's choosing (such as: clicking on a link that was sent to them via email or someplace else)

A Successful Attack can compromise user data and the website as well (since the attacker can easily change the account password and linked email/phone/both). Although it is hard to do for the reason that most places would confirm such steps with Multi-Factor Authentication that includes signature and face-2-face authorisation.

## Possible Damage to User
1) Loss of control over an account connecting to a service like (Bank Account).
2) Loss of data from the website/service of the account
3) Manipulation of User/Customer Data and Information
4) Identity theft for limited or long periods of time.

---
# How does CSRF work?
Basically, the attacker aims to perform a [[Session Hijacking\|Session Hijacking]] or [[Session Spoofing\|Session Spoofing]] attack by sending emails to legitimate users to visit their fraudulent clone website.

On this Website, the user is asked to enter their credidentials like UserID, Password among any other possibly required credidentials or CAPTCHA & if the attacker's goal is [[Session Spoofing\|Session Spoofing]] or [[Identity Theft\|Identity Theft]] then the clone website either stores these credidentials or has a bot which enters these credidentials into the actual website's login page to login as the legitimate user and get the account for themselves by changing the password and the recovery email. In other cases, if the goal is [[Session Hijacking\|Session Hijacking]], then these credidentials are used to conduct ONE specific command. (like transfer of money) 

---
# How is CSRF combined with Phishing to steal from Bank Accounts?
1. The Attacker forges a request for a fund transfer to some website i.e., the request is fake and the money is going to attacker's account.
2. Attacker embeds the hyperlink into a message that is sent to users who may be logged in.
3. Visitor clicks on the link being diverted to the payment gateway of the "website".
4. Website validates request and transfers money from visitor's account to attacker.

![CSRF.png](/img/user/Vaulted%20Images/CSRF.png)

---
# Prevention against the CSRF Attack
1. The most robust way to defend against CSRF attacks is to include a [[CSRF token\|CSRF token]] within relevant requests. The token should be: 
	1. Unpredictable with high entropy, as for session tokens in general.
	2. Tied to the user's session.
	3. Strictly validated in every case before the relevant action is executed.
2. Use of value which is known to the user only for each transactions.

---
# Footnotes
1. 