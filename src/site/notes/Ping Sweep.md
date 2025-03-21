---
{"dg-publish":true,"permalink":"/Ping Sweep/","tags":["CompSci","CyberSec","CompNet","EthHack"]}
---


---
# Ping Sweep
> Checks for Live Users & machines in an entire network by using [[ICMP\|ICMP]] Exho Request to all the IP Addresses in the Network Range and generate a list of all IP Addresses with individual RTT of the Echo Request and Reply for individual IP Address.

Hence, it helps to map out an entire network. You would still need tools to draw Network Maps like with [[Vulnerability Scanning\|Vulnerability Scanning]].

Possible Security Implicators:
1. **Network Visiblity**: The person carrying it out (if an attacker) knows all the IP Addresses.
2. **False Alarms**: Even if the [[Network Administrator\|Network Admin]] is doing this, it can trigger an alarm with the IDPS.

---
# Footnotes