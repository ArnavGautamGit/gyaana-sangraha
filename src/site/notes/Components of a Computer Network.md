---
{"dg-publish":true,"permalink":"/Components of a Computer Network/","tags":["CompNet","Academics"]}
---


---
# Components of a Computer Network

A Computer Network has two main components:
1. ***The Network Edge***: Phones, PCs, Consoles etc.
2. ***The Network Core***: Packet Switches etc.

Also the Network Architecture also has various types of Delays and Losses and its speed is measured using a metric known as 'Throughput' (see [[Components of a Computer Network#^1\|#^1]])
## The Network Edge
- The edge of the network.
- Edge (here) refers to the end-user devices like Mobile Phones, Personal Computers etc.
- Every computing device that can run applications or host them are now called *"hosts"*.
	- Hosts are further divided into clients and servers.
	- Clients use the websites, email etc.
	- Servers distribute websites, relay email, stream video etc.
	- Servers are more powerful machines residing inside large ***data centres***.
- Multiple PCs are connected to each other using LAN cables (RJ45 Ethernet connector).
- Each PC is connected to another PC using Switches and Hubs. (please see [[Computer Networks#^0a01f6\|Computer Networks#^0a01f6]] and [Network Nodes](https://en.wikipedia.org/wiki/Computer_network#Network_nodes))
- Sometimes PCs may be connected Wirelessly by Wireless LAN (also called WiFi) where you can read more about it on [The Wikipedia Page](https://en.wikipedia.org/wiki/Computer_network#Network_links).
- Now, the Network may need to connect to other networks which may be somewhere else. For that reason, one of the edge nodes of the network is a Router. (see [[Computer Networks#^dffab0\|Computer Networks#^dffab0]])
- There are 3 kinds of Addresses Possible on this kind of a network: Physical, Logical and Port. (see [[Application Layer#What are Addresses?\|Application Layer#What are Addresses?]])
### Understanding Networks using the Analogy of Telephone lines.
In the early days, calls were not automated, we would call a PSTN, tell them the person and number we wanted to connect to and then the attendant at the PSTN would manually connect us with the person of our choice.
The Manual connection used to happen on a switch.
The connnecting wire is analogous to LAN/Ethernet cables.
### Physical Media
1. ***==Twisted-Pair Copper Wires==***: Consist of two insulated copper wires, each about 1mm thick and arranged in a regular spiral pattern. The wires are twisted together to reduce the electrical interference fropm similar such wires nearby. These have been used for more than 100 years in the Telephone Industry. Unshielded Twisted Pair (UTP) are still used in LANs today giving speeds between 10 Mbps to 10 Gbps. the data rates that can be achieved depend heavily on wire thickness and distance of transmitter to the receiver
2. ***==Coaxial Cables==***: Consist of two copper conductors but thety are placed concentrically rather than parallely - achieving higher data transmission rates. Were used in old TVs
3. ***==Fiber Optics==***: Glass Wires that carry the data in form of pulses of light inside them using Total Internal Reflection.
4. ***==Terrestrial Radio==***: No wires needed, Electromagnetic Radio waves go through or bend around walls. More convenient. Wireless mouse use very small range (few metres). Followed by Wireless Local Area Networks (WiFi) going up to a few hundred metres. Then Wide Area Networks (WAN) that span kilometers.
5. ***==Satellite Radio==***: Beter for remote areas. Satellite links can operate at massively fast speeds. Due to its height, it can serve more people with one transmitter.
## The Network Core
All nodes are not directly connnected.
The Network Core uses two ways of passing packets from one node to another:
1. Packet Switching
2. Circuit Switching
### Packet Switching
- To send a message from a source end system to a destination end system, the source breaks long messages into smaller chunks of data called "Packets".
- The packets travels through many packet switches i.e., routers and link-layer switches.
- Each movement from one intermediary router to another (except source and destination routers) is called a "hop".
- If $L$ packets are transferred over a rate of $R$ bits/second, then the transmission time is $\dfrac{L}{R}$.
- At the destination router, the packets are reassembled (see [[Intrusion Detection and Prevention#^3\|Intrusion Detection and Prevention#^3]])
### Circuit Switching
- Before the sender can send the info, the network must establish a connection between the sender and receiver. 
- This is a bona fide connection for which switches on a path between the sender and receiver maintain connection state for that connection.
- This connection is called a ***circuit***. When the circuit is established, a constant transmission rate is also reserved for the duration of the connection.
- The System reserves specific link/path for ***end-to-end connection***.
## Packet Switching vs Circuit Switching
| ***PACKET SWITCHING*** | ***CIRCUIT SWITCHING*** |
| ---- | ---- |
| Simpler than Circuit Switching | More reliable for real-time services like calls |
| ***Highly Flexible*** - can handle different data rates and packet sizes | ***Guaranteed Bandwidth*** - reserves a path for the connection. |
| Higher Latency and Unpredictable Performance | ***Predictable Performance*** with ***low latency*** |
| ***More Scalable*** than Circuit Switching technique. | Not as scalable as the Packet Switching technique. |
| ***Less Costly*** to implement for developers | More Expensive to implement |
| ***More Efficient***. Resources allocated only when data transfer takes place.<br>(Can host 3x more users with same performance as Circuit Switching) | ***Inefficient Bandwidth use***, path is still reserved when no data is being transferred. |
| ***Prone to Packet Loss*** due to congestion on the network. |  |
## Types of Delays in Computer Networks
1. ***==Nodal Processing Delay==***: Time taken to examine a packet's header and which next node it is supposed to be sent to. 
2. ***==Queuing Delay==***: The time spent by the packet waiting to be transferred onto the link.
3. ***==Transmission Delay==***: The amount of time required to push all of the packet's bits into the link. It is equivalent to the previously mentioned ratio of $\dfrac{L}{R}$ used to calculate Transmission Time.
4. ***==Propagation Delay==***: Time required to propagate from the beginning of the link to router B.

The sum of all four makes the ***==Total Nodal Delay==***. 
There is another type of Delay, called the End-to-End Delay, defined as the sum of Processing, transmission and Propagation delays.
### Transmission Delay vs Propagation Delay
The transmission delay is the time needed for the router to push out the packet. It does not account for the distance the packet has to travel from Router A (starting router) to Router B. It is dependent only on Packet Length and rate of Transmission.
Propagation Delay is the time it takes to propagate from one router to another. 
It is dependent upon the distance between the routers, not the packet length (longer packet takes longer to send).
Hence, it can be said that Transmission Delay is the opposite of Propagation Delay in some matters.

---
# Footnotes
1. Taken from [[Throughput#Throughput in Computer Networks\|Throughput#Throughput in Computer Networks]]
{ #1}

2. 