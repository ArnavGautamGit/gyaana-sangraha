---
{"dg-publish":true,"permalink":"/Computer Networks/","tags":["Academics","CyberSec","CompNet"]}
---

***Created on: 04/10/2023
Last updated: 04/10/2023***

---
# What is a Computer Network?
A Network, in computing terms, is an interconnected web/net of multiple autonomous computers that create an infrastructure that provides services to applications. Example: JIITs Computer Network distributed across multiple labs and probably around 500 computers which can run applications like StarUML and CodeBlocks.

> A computer is considered ***"Autonomous"*** if it can make decisions on its own discretion and can perform computations independently (using only its own CPU unit).

Any Computer Network runs based on certain protocols.

> A **_==Protocol==_** defines the format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.

See also: [[Layers of Computer Networks\|Layers of Computer Networks]]

---
# Technology used in creation of Networks
Chronologically, the technology involved in Networks is as follows:
1. ***[Repeaters](https://en.wikipedia.org/wiki/Repeater)***: A piece of technology that extends the range of a signal by repeating the signal on a higher wavelength to transmit farther.
2. ***Hubs***: Massive equipment used to interconnect all network computers using individual LAN cables from each that go into the hub - every PC is connected to every PC.
3. ***[Bridges](https://en.wikipedia.org/wiki/Bridging_(networking))***
4. ***[[Computer Networks#^3\|Switches]]***: Similar looking but better than Hubs. Used in all JIIT Labs nowadays. Switches are better since it removes unnnecessary connnection (every PC need not be connected to every other PC in the system. 12 PCs will create 144 connections, instead of 13 when connected linearly).
{ #0a01f6}

5. ***Router***: The same as our WiFi router used to connect different networks together using IP address and port number pairs of sender and receiver. Routers are able to do this by using '[[Routing\|Routing]]'.
{ #dffab0}

6. ***Gateways***: Acts as a protocol converter. If sender uses IPv4 but the receiver uses IPv6, the Gateway helps both the networks converse by inter-converting between the protocols.

See Also: [[Components of a Computer Network\|Components of a Computer Network]]

---
# What is Packet Loss?
We know that the queues to send packets onto a link are finite, hence when the queue is fully filled, the next $\large(n+1)^{th}$ packet gets deleted/dropped i.e., lost.
In Network lingo, it is called Packet Loss.
This has to be done since the packet has nowhere to go and the router does not have storage of its own...

---
# What are Network Addresses?
A PC has certain unique addresses that can be used to identify it.
1. IP Address - Internet Protocol Address (check [[IPv4 Addressing\|IPv4 Addressing]] for more)
2. MAC Address
3. Port Address - each port is assigned a unique one.
Multiple IP addresses are possible if there are multiple WiFi networks available (my house has 2 WiFi for example)
Multiple Port addresses are easily possible since  a PC may have multiple tabs open on the internet, each tab has a separate, unique port number.
==BUT There can ONLY be ONE, SINGULAR, UNIQUE MAC ADDRESS for a specific computer. Although more and more computes are ditching its use.==

---
Next Chapter in FOCS ---> [[Intrusion Detection and Prevention\|Intrusion Detection and Prevention]]
Next Chapter in CompNet---> [[Layers of Computer Networks\|Layers of Computer Networks]]
# Reference Material
2. 
{ #2}

3. [The Wikipedia Page](https://en.wikipedia.org/wiki/Computer_network#Network_links) for Computer Networks mentions Repeaters and Hubs, Bridges and Switches as 2 dual-component systems where both the components need to work together.
{ #3}



