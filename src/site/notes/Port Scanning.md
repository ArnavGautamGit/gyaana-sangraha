---
{"dg-publish":true,"permalink":"/Port Scanning/","tags":["CompSci","CyberSec","CompNet","EthHack"]}
---


---
# Port Scanning
> The Process of attempting to contact each and every [[Network Port\|Network Port]] on the target system to see which one is open & hence allows the scanner to see which services are working on the [[Scanning#^1\|TOE]].

Often used by hackers to narrow down the types of attacks they cannot do due to those specific ports being closed & the attacks that may be possible due to the port being open - but the final decision is only made after [[Network Scanning\|Network Scanning]] is complete.

The most popular Port Scanning Tools are [[Nmap\|Nmap]] and [[hping\|hping]] although other tools exist.
### How does it crack which OS target is using?
It figures out the [[Operating System\|Operating System]] of the target since certain Operating Systems are identifiable using Ports if the ports 137 to 139 are open means the system is running NetBIOS - only used when Windows system needs to communicate with Linux, so the target is Windows and it is communicating with other Linux Machines on the network - most popular OS for servers is [[Ubuntu\|Ubuntu]] (Linux).

### Countermeasures
- Configure Firewall and IDS to Detect & Block probe attempts.
- Run the port scanning tools against hosts on the network to determine whether the firewall properly detects the port scanning activity.
- Ensure that the router, IDS, firewall are updated to their latest releases.
- Use custom rules set to lock down the network and block unwanted ports at the firewall.
- Ensure that anti-scanning and anti-spoofing rules are configured.

---
# Footnotes