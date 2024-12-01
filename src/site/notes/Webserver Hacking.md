---
{"dg-publish":true,"permalink":"/Webserver Hacking/","tags":["Academics"]}
---


---
# Webserver Hacking
> An Attack aimed at taking control of (or destroying) any target webservers or at least making them unavailable for some finite period of time.

Webservers using Linux on the internet are called "Open Web Servers". since Linux is Free and Open Source Software (FOSS).
Webservers using Windows are called as IIS Web Servers where IIS stands for "Internet Information Server". 

## Popular Attacks against Webservers
1. [[DOS Attack\|DOS Attack]] and [[DDOS Attack\|DDOS Attack]] - Used to make the server unavailable and kill the websites.
2. [[Cross Site Scripting (XSS) Attack\|Cross Site Scripting (XSS) Attack]] - Using another website to run browser scripts on target
3. [[CSRF Attack\|CSRF Attack]] - Similar to Phishing.
4. [[SQL Injection Attack\|SQL Injection Attack]] - Attack the database/server by entering SQL into website's input fields.
5. [[Man-in-the-Middle Attack\|Man-in-the-Middle Attack]] - Used to sniff the packets (probably using ARP sniffing).
6. [[DNS Hijacking Attack\|DNS Hijacking Attack]] - Compromising DNS server by DNS cache poisoning.
7. [[DNS Amplification Attack\|DNS Amplification Attack]] - Leverages DNS recursive method. Lookup address of the DNS is poisoned.
8. [[Directory Traversal Attack\|Directory Traversal Attack]] - Trying to access restricted directories on trial and error basis.
9. [[Phishing\|Phishing]] - Luring the users to another similar looking website to extract Login Details.
10. [[Website Defacement\|Website Defacement]] - hacking into and chnaging how the website looks and changing its function.

## Vulnerability Types
There can be many Vulnerabilities in the webserver which also form the reason why they get compromised (if the vulnerabilities are hit). These Vulnerabilities can simply be divided into the following 3 categories: 
1. Security vs Comfort
2. Poor Security
3. Misconfiguration

#### Vulnerability Type 1: Security vs Comfort
- Security conflicts with business ease-of-use case
	- Presence of self-signed certificates and default certificates.
	- Running servers with default settings
	- Running of unnecessary services (management and remote admin etc.)

#### Vulnerability Type 2: Poor Security
- Poor security policy, procedures, and management
	- Presence of default accounts (with no passwords)
		- Hackers can easily remote login as admin
	- Keeping unnecessary default, backup, or sample files
		- Hackers can replace sample files with their own files to create backdoor entry.
	- Enabling of administrative debugging functions
		- Hackers can run commands on your server from outside your office.
	- Improper file and directory permissions
	- Bugs in server software, OS, and web applications

#### Vulnerability Type 3: Misconfiguration
- Misconfiguration of one or more of the following:
	- SSL Certificate
	- Webserver or its [[Operating System\|Operating System]]
	- Websites and WebApps hosted on it

## Hacking Procedure
1. Information Gathering and [[Footprinting\|Footprinting]]
2. Website [[Enumeration\|Enumeration]]
	1. Use Nmap commands like the following
		1. `Nmap -sV -o -p [Target's IP Address]`
		2. `Nmap -sV -script=http-enum [Target's IP Address]`
		3. `Nmap [Target's IP Address] –p 80 –script=http-frontpage-login`
		4. `Nmap –script http-password –script-args http-password.root =/ [Target's IP Address]`
3.  Website Mirroring and [[Vulnerability Scanning\|Vulnerability Scanning]].
4. [[Session Hijacking\|Session Hijacking]] and Hacking Web Passwords.

## Countermeasures
- Keep Webservers in a Publically Accessible area but make sure the area is secure by adding Firewalls just like Public Transit has security checks by Police.
- Apply all updates
- Take regular backups
- Block unnecessary ports, ICMP traffic, NetBIOS and SMB.
- SMTP, FTP, Telnet etc are unsafe protocols, avoid using them. Use [[IPSec (IP Security)\|IPSec (IP Security)]] instead.
- Run websites with least privileged accounts.
- Perform regualr security audits
- Eliminate unnecessary files within the .jar files
- Eliminate sensitive configuration information within the byte code
- Avoid mapping virtual directories between two different servers, or over a network
- Monitor and check all network services logs, website access logs, and database server logs frequently.
- Disable serving of directory listings
- Eliminate the presence of non web files in the webserver

---
# Footnotes