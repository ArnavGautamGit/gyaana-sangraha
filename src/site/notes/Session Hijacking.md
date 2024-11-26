---
{"dg-publish":true,"permalink":"/Session Hijacking/","tags":["Academics","CyberSec","EthHack"]}
---


---
# Session Hijacking
Before we understand what Session Hijacking is, we must understand what a session is.
***Definition of a session***:
> A connection formed between client and server established after user entered their user id and password on the client PC connecting to the server.

Now that we know what a Session is,
***Definition of Session-Hijacking***:
> Process of taking over a legitimately established session by using (but not limited to) techniques like [[Cross Site Scripting (XSS) Attack\|Cross Site Scripting (XSS) Attack]] and [[CSRF Attack\|CSRF Attack]].

Session Hijacking was a big problem back in the day when no countermeasures were known. It is a short-term, one-time variant of [[Session Spoofing\|Session Spoofing]] which includes taking long-term control over the account.

### Root Causes
The Following reasons are the root cause why Session Hijacking Attacks are successful against the website/software/service to be secured:
- NO account lockout for invalid session IDs
- Insecure Handling of Session ID and Password (no hashing)
- Weak session ID generation algorithm
- Indefinite session expiration time (Sessions must expire after X amount of inactivity) i.e., [[Cyber Security Principles\|Principle of Adequate Protection]]
- Small session ID Length.



---
# Footnotes