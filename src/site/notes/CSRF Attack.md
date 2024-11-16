---
{"dg-publish":true,"permalink":"/CSRF Attack/","tags":["Academics","CyberSec"]}
---


---
# Cross-Site Request Forgery (CSRF) Attack
CSRF is an attack which involves duping an end user into performing unwanted tasks on a website they are currently logged/authenticated in.
With the help of [[Social Engineering\|Social Engineering]], one can easily make the user perform actions of the attacker's choosing (such as: clicking on a link that was sent to them via email or someplace else)

A Successful Attack can compromise user data and the website as well (since the attacker can easily change the account password, unlink the other's email & link his email instead). Although it is hard to do for the reason that most places would confirm such steps with Multifactor Authentication that includes signature and face-2-face authorisation.

Most of the times, this is nowadays used as a one-time attack to deduct the money from the accounts of the victim. It is not used as an elaborate scheme anymore.

## What is the objective of the CSRF Attack?
1) transfer the money from one bank to another
2) use a content management system to add/delete content from a website 
3) change passwords 
4) manipulate user/customer information, etc.

---
# How does CSRF work?
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