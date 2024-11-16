---
{"dg-publish":true,"permalink":"/DDOS Attack/","tags":["Academics","CyberSec"]}
---


---
# Distributed Denial of Service (DDOS) Attack
It is a type of [[DOS Attack\|DOS Attack]] but it is done with many PCs.
Multiple PCs are infected using a [[Computer Virus\|Virus]] or [[Computer Worm\|Worm]] to create Botnets/Zombies that can attack a website volumetrically and deny service. It was also done rather famously in [[Code Red (Worm)\|Code Red (Worm)]] Attack when USA's White House website was hit with DDOS attacks enabled by all PCs that were hit with Code Red & converted to botnets. 

Due to the sheer volume of PCs attacking at the same time, there is no wayt to track where the attack originated from and who were the attackers unless they specify themselves.

---
# Techniques used in DOS & DDOS attacks
The style of attacks we studied in the previous section are known as ***Volumetric Attacks***
Other Styles of DOS and DDOS Attacks with other techiques do exist They are given in a list below:
1. ***==Fragmentation Attacks==***: Small IP datagrams are sent to your Router from singular/many sources, IP Packet Reassembly takes time and it will slowly slow down your Router. Enough volume can brick the router. SImilar attacks can be done with TCP, UDP or ICMP packets.
2. ***==Application Layer Attacks==***: Programs in the [[Application Layer\|Application Layer]] are targeted and attacked, so that they stop responding & get damaged beyond serviceability.
3. ***==Service Flooding Attakc==***: Floods the servers with requests demanding service. The number eventually becomes beyond the amount what the server can handle, and it gets overwhelmed.
4. ***==SYN Flooding Attack==***: Sends an immense amount of TCP SYN requests which overwhelm the servers with a huge number of clients.
5. ***==ICMP Flooding Attack==***: A large amount of ICMP requests which will not give enough time to the server to address each request.

---
# Defensive Strategies against DOS and DDOS
1. Disable unnecessary services from the Task Manager
2. ***==Use Anti-Malware (also called "Anti-Virus")==***: Always enable real-time protection provided by operating systems.
3. ***==Enable Router Throttling==***: Allows time buffer for admins to respons in a DDOS attack situation.
4. ***==Use a reverse proxy==***: Opposite of Forward Proxy, Middle server will take the DDOS attack/any load while the Original Server is still fine.
5. ***==Enable Firewall's Ingress & Egress filtering==*** which filter incoming & outgoing traffic respectively and protect from being hit with DDOS and also from being used as a botnet. Firewalls filter out any repetitive requests for connetion. A good firewall can even stop [[Ping\|Ping]] and [[Ping Sweep\|Ping Sweep]] if needed.
6. ***==Use Degrading Services==***: which degrade rights and power of services which are no longer being used or specific ones that are marked.
7. Last option is to absolutely ***==absorb and devour the attack itself==*** by adding more and more power on your server which requires more and more devices from the attackers to take you down. If you can maintain server power that can handle a big chunk of the world's devices then you can fail any DDOS attempt. 

---
# Footnotes