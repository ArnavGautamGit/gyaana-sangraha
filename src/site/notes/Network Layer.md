---
{"dg-publish":true,"permalink":"/Network Layer/","tags":["CompSci","CompNet"]}
---

# Index/Contents
[[Network Layer#What is Network Layer?\|#What is Network Layer?]]
[[Network Layer#What is Network Layer?\|#What is Network Layer?]]
[[Network Layer#What is the Internet Protocol (IP)?\|#What is the Internet Protocol (IP)?]]
[[Network Layer#What is the measure of Network Layer Performance?\|#What is the measure of Network Layer Performance?]]
[[Network Layer#Congestion Control in Network Layer\|#Congestion Control in Network Layer]]
[[Network Layer#Footnotes\|#Footnotes]]

-----
# What is Network Layer?
The Network Layer is located between Transport Layer and Data Link Layer. It provides services to Transport Layer and receives services by the Data Link Layer.
Packets in this layer are referred to as *"Datagrams"*.

There are many smaller protocols used in this layer (like [[Network Layer#^IGMP\|#^IGMP]], [[Network Layer#^ICMP\|#^ICMP]], [[Network Layer#^ARP\|#^ARP]]) but by far the biggest and the most common protocol is the Internet Protocol (IP) which is the backbone of this layer - if not Networking as a whole.

We will be majorly studying about IP and IP Addresses only throughout this Chapter.

---
# What is the Internet Protocol (IP)?
This is the layer that carries data across Network Layer in specific datagrams.
It is also responsible for carrying UDP Packets a lot of the times. It was studied here: [[Transport Layer#User Datagram Protocol (UDP)\|Transport Layer#User Datagram Protocol (UDP)]]
***Packets*** in this layer are referred to as *"Datagrams"*.
***Sockets*** that are extensively used in the above layers are actually made in this layer and also exist in this layer.
## IP Datagram Header
Each IP Datagram contains a header and packet data. The Header is minimum 20 bytes and the maximum length it can achieve is 60 bytes.
![IP Packet Header.png](/img/user/Vaulted%20Images/IP%20Packet%20Header.png)
- ***==Version (VER)==*** defines Version (IPv4 or IPv6). Its value is either 4 or 6 in binary (0100 or 0110).
- ***==Header Length (HLEN)==*** defines Header Length (could be 20-60 bytes)
- ***==Service Type==*** also called as [[Network Layer#^DSCP\|#^DSCP]] is used to specify the Quality of Service desired for the packet. Its 8 bits are divided into 6 bits of Codepoint and 2 bits of Data 
- ***==Total Length==*** defines total length of this frame (packet + header)
- ***==Time to live (TTL)==*** defines the maximum number of hops a packet is allowed before it is discarded. 
- ***==Protocol==*** defines the service the packet is serving (SMTP, or any other application)
- Both Source and Destination IP Adresses are 32 bits each

Other important terms are in the scan below:
![IP Packet Header 2.png](/img/user/Vaulted%20Images/IP%20Packet%20Header%202.png)

---
# What is the measure of Network Layer Performance?
Delay is considered the best measure for performance in the Network Layer as well.

Queuing Delay is waiting in input and output queues of a router
Processing Delay is the time required to read packet's header (and send it towards its destination)
Propagation Delay is the Distance/Propagation Speed
Transmission Delay is the Packet Length/Transmission Rate
$$\large Total \ Delay = (n+1)(TD + PropD + ProcD) + n(QD)$$
$\large where \ n = number \ of \ hops$

Throughput is also used as a measure, keep in mind Throughput (here) is:
> ***Throughput (here) is defined as the minimum of all Transmission Rates of all routers in the network/path i.e.,  $Throughput = minimum(TR_1 + TR_2 + TR_3 +...)$***

This is the definition taken from the "derived definition" in [[Throughput#Throughput in Computer Networks\|Throughput#Throughput in Computer Networks]]

---
# Congestion Control in Network Layer
See the definition of Congestion Control in [[Transport Layer#What types of Controls are implemented on the Transport Layer?\|Transport Layer#What types of Controls are implemented on the Transport Layer?]]
Congestion can occur in any layer of Computer Networks and the Network Layer is no different. Refer to [[Random Access Protocols\|Random Access Protocols]] where protocols like Aloha, CSMA/CD & others were used to combat congestion and collisions in the network.

---
Next Chapter --->[[IPv4 Addressing\|IPv4 Addressing]]
# Footnotes
1. ***IGMP*** also called as the ***Internet Group Messaging Protocol*** used for Group Communication and Broadcasting messages.
{ #IGMP}

2. ***ICMP*** also called as the ***Internet Common Messaging Protocol*** used for messaging and Network Management.
{ #ICMP}

3. ***ARP*** also called ***Address Resolution Protocol*** is used for communication protocol when MAC Address is not known but IP Address is known. It is a communication protocol which allows to discover the link layer MAC Address when an IPv4 Address is known.
{ #ARP}

4. ***DSCP*** also called as ***Differentiated Services Code Point***. It has 8 bits in the IP Datagram Header. It defines the Quality of Service that will be provided to the IP Datagram Frame. The first 3 bits are used as Class Selectors and are used to indicate Traffic Class. 000 stands for Default or Best Effort where as 001 to 111 stand for Class 1 to Class 7. The next 2 bits are used as Drop Precedence which indicate the relative importance of packets within a class (defined in first three bits) and by extension, which packets to be dropped first. The Fifth bit is currently unused whereas the last two bits are used or Explicit Congestion Notification (ECN). ECN allows for end-to-end notification of network congestion without dropping packets. The ECN bits can have the following values:
{ #DSCP}

	- 00: Not ECN-Capable Transport (Not-ECT) 
	- 01: ECN-Capable Transport (ECT) 
	- 10: ECN-Capable Transport (ECT) 
	- 11: Congestion Experienced (CE). 
5. 

