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

Session Hijacking was a big problem back in the day when no countermeasures were known.

### Root Causes
The Following reasons are the root cause why Session Hijacking Attacks are successful against the website/software/service to be secured:
- NO account lockout for invalid session IDs
- Insecure Handling of Session ID and Password (no hashing)
- Weak session ID generation algorithm
- Indefinite session expiration time (Sessions must expire after X amount of inactivity) i.e., [[Cyber Security Principles\|Principle of Adequate Protection]]
- Small session ID Length.

### Various Types
- ***Session Sniffing***: Attackers find session IDs by aiming their sniffing on specific target (s). 
- ***Predicting Session Tokens***: Making an educated guess by looking at the session tokens and trying to crack a pattern (if any).
- ***Man-in-the-middle Session Hijack***: Attacker intercepts a session directly. 
- ***Man-in-the-browser Session Hijack***: Attacker uses browser scripts or mallicious extensions among other known attacks like [[Cross Site Scripting (XSS) Attack\|Cross Site Scripting (XSS) Attack]].

### Network Layer Session Hijacking
While other types seen in [[Session Hijacking#Various Types\|#Various Types]] were Session Hijacking attacks based in the [[Application Layer\|Application Layer]], it is important to note that Session Hijacking can also be [[Network Layer\|Network Layer]]-based where the objective is to hinder the functionalities at Network Layer and [[Transport Layer\|Transport Layer]].

There are a lot of types of Network Layer Session Hijacking.
1. ***TCP/IP Session Hijack***: Predicting the TCP/IP sequence numbers.
2. ***RST Hijacking***: Sending RST signal to the server with victims spoofed IP address and predicted packet sequence number.
3. ***UDP Hijacking***: The objective is to fool the target to mistake the attacker’s machine as the server. Attacker will send faster response than the server to make the target believe attacker is the server.

### Countermeasures
- Use Network Monitoring services like an [[Intrusion Detection and Prevention System (IDPS)\|IDPS]] & monitor ARP Broadcast Traffic Anomalies.
- Disable auto-running of scripts in the browser.
- Always check permissions needed by the extension before using.
- Use stronger [[Authentication\|Authentication]] mechanisms such as [[Kerberos\|Kerberos]].
- Use technologies such as [[IPSec (IP Security)\|IPSec (IP Security)]] and [[Secure Sockets Layer (SSL)\|SSL]] in applications and websites.
	- IPSec basically is used to establish a [[Virtual Private Network (VPN)\|VPN]] to secure the [[Objectives of Cyber Security\|Objectives of Cyber Security]] for IP Traffic.
	- IPSec is comprsed of a minimum of three algorithms 
		- A [[Symmetric Key Encryption\|Symmetric Key Encryption]] Algorithm for [[Confidentiality\|Confidentiality]]
		- A [[Hashing\|Hashing]] Algorithm for [[Integrity\|Integrity]]
		- Some form of [[Authentication\|Authentication]], generally via [[Digital Signatures\|Digital Signatures]].


---
# Footnotes