---
{"dg-publish":true,"permalink":"/Application Layer/","tags":["Academics","CompNet"]}
---


----
# Index/Contents
[[Application Layer#Application Layer\|#Application Layer]]
[[Application Layer#What are the known Application-Layer Architectures?\|#What are the known Application-Layer Architectures?]]
[[Application Layer#What are Addresses?\|#What are Addresses?]]
[[Application Layer#What are some Criteriae for Transport Protocols?\|#What are some Criteriae for Transport Protocols?]]
[[Application Layer#What is DHCP? Basics of DHCP\|#What is DHCP? Basics of DHCP]]
[[Application Layer#What is TCP? Basics of TCP\|#What is TCP? Basics of TCP]]
[[Application Layer#All about Web & HTTP\|#All about Web & HTTP]]
[[Application Layer#What are Cookies? (limited discussion)\|#What are Cookies? (limited discussion)]]
[[Application Layer#What is a Web Cache/Proxy Server?\|#What is a Web Cache/Proxy Server?]]
[[Application Layer#EMAILs and SMTP - How does email work?\|#EMAILs and SMTP - How does email work?]]
[[Application Layer#What is Domain Name Service (DNS)??\|#What is Domain Name Service (DNS)??]]
[[Application Layer#Footnotes\|#Footnotes]]

Whenever free: Add to the notes of DHCP, TCP, HTTP, SMTP and DNS and redirect to those notes. If there is nothing to add, just redirect to those notes.

-----
# Application Layer
> The topmost layer in [[Computer Networks\|Computer Networks]] where [[Authentication\|authenticated]] and [[Authorisation\|authorised]] users interact with Network Applications available on this network.

Every Application Layer App is fed information about what it is to be displayed by the [[Transport Layer\|Transport Layer]]. For Example: many important [[Application Layer\|Application Layer]] protocols such as the [[Simple Mail Transfer Protocol (SMTP)\|SMTP]] use Transport Layer protocols such as [[Transmission Control Protocol (TCP)\|TCP]].

### What are the known Application-Layer Architectures?
The Network Applications - including applications that access the internet or need the internet to study. There exist two major types in contemporary Compter Networks:
1. Client-Server Architecture
2. Peer-to-Peer Architecture (also called "P2P")
3. Hybrid Architecture

See: [[Network Application Architecture\|Network Application Architecture]] for more information on Individual Types.

---
# What are Addresses?
As we just read, 

> "A Socket can be considered analogous to a door with a unique number. That unique number is the Port Address."

There is also a Logical Address (IP Address) which is governed by [[IPv4 Addressing\|IPv4 Addressing]] and while there can be multiple Ports creating multiple Port Addresses and multiple LAN cards creating multiple IP Addresses (Using [[IP Classful Subnetting\|IP Classful Subnetting]] and [[IP Classless Subnetting\|IP Classless Subnetting]]), ***==there can only be one Physical Address (also called "MAC Address")==*** although MAC Addresses are dissappearing due to the slow disappearance of Wired Networks and LAN cards from newer systems as a whole. IP Addresses are not going anywhere since WIFI cards still have them. It will still take time for Wired to completely disappear, but it won't take that long either.
# What are some Criteriae for Transport Protocols?
Copy Paste this entire section in Transport Layer.
1. ***==Reliable Data Transfer==***: A protocol that provides a guaranteed data delivery to the receiver, it is said to provide Reliable Data Transfer. Loss-tolerant Apps lack this service.
2. ***==Throughput==***: Certain apps that are inelastic (i.e., Bandwith Sensitive Apps) may have a certain limit on minimum bandwith connection. Some may alter the content's quality according to the throughput. There are many that are elastic applicatiuons that use as muych or as less of Throughput is available. If you haven't read, we learnt about throughput in the last chapter (see [[Throughput#Throughput in Computer Networks\|Throughput#Throughput in Computer Networks]] for more info)
3. ***==Timing==***: Such a service is very appealing to real-time apps that have high timing constraints on data delivery for it to be effective i.e., something like interactive games or video-calling/video-conferencing apps.
4. ***==Security==***: transport protocol providing one or more security services. A transport protocol can encrypt all messages transmitted by the sending process, and the transport-layer protocol can decrypt the data before delivering it to the other side.
# What is DHCP? Basics of DHCP
Dynamic Host Configuration Protocol (DHCP) is a client-server protocol designed to provide the four pieces of information for a diskless computer so that the host may configure itself after booting for the first time.

If the server is in a different network, every router will discard its broadcast reply (since it uses a broadcast address to inform all systems of the Host-Configuration info, it cannot). It needs to use a relay agent. The agent knows the unicast address of DHCP server and hence is able to listen to incoming messages on port 67.

If the server is located in the same network (rare case):
1. The DHCP issues a passive open channel command on UDP port 67 and waits for client.
2. A booted client issues an active open commmand on port 68. The message is encapsulated in a UDP user datagram with port number (source) being 68 and destination being 67. The client uses all 0s for source address and all 1s for server address.
3. The server responds with broadcast or unicast message on the same ports as above. The unicast response can be cast since the server knows the IP address of the client.

---
# What is TCP? Basics of TCP
The TCP service is model includes a connection-oriented service and reliable data transfer service. Check back on the [[Application Layer#What are some Criteriae for Transport Protocols?\|#What are some Criteriae for Transport Protocols?]] to see what these mean in full.
- ***==Connection-Oriented Service==***: After the 3-step handshake is done, the TCP connection is said to be established. This connection is full-duplex (duplex means double-sided and full means both can send packets simultaneously).
- ***==Reliable Data Transfer Service==***: all data is sent in proper order without error. It also includes congestion control mechanism - it throttles a sending process when network is congested.
- TCP uses IP Addresses to identify what is the source and what is the destination and where it is located. Which is also why it is called as TCP/IPmany times.

---
# All about Web & HTTP
- HyperText Transfer Protocol (HTTP) is implemented in both client and server programs, executing on different systems talk to each other by exchanging HTTP messages. 
- HTTP defines the structure of these messages and how the client and server exchange the messages.
- A webpage consists of objects (files) that may be HTML, JPEG, JavaScript or something different.
- HTTP uses TCP as its underlying transport protocol.
- The Client and Server can form a connection. Once formed, the connection allows the client to send messages asking for certain files, and HTTP responding from its socket about the availability.
- TCP transports these messages from client to server and vice-versa. 
- TCP is preferred over UDP since it guarantees Reliable Data Transfer.
## Non-Persistent vs Persistent Connections
 For non-persistent connections, the TCP connection is closed after every object is sent i.e., if 10 objects need to be sent, there will be a total of 11 connections made. Where, one connection lasts for precisely 1 request and 1 reply.
 We also need to find Round Trip Time (RTT) for comparison purposes.
 ***RTT = Propagation + Queuing + Processing Delays***
Non-Persistent takes 2 RTTs: 1 to establish connection and one to send/receive a single object. To send/receive $\large n$ objects, it requires $\large (n+1)$ RTTs.

For Persistent Connections, no TCP buffers are allocated here (unlike non-persistent) and server holds connection. i.e., less RTTs! Due to a persistent TCP connection, Requests can be made back-to-back without waiting for pending requests to be completed first.
## HTTP Message Format
HTTP Request:
```HTTP
GET /someDirectory/page.html HTTP/1.1
Host: www.randomschool.edu
Connection: close
User-agent: Mozilla/5.0
Accept-language: en
```

HTTP Response:
```HTTP Response
HTTP/1.1 200 OK
Connection: close
Date: Tue, 18 Aug 2015 15:44:04 GMT
Content-Length: 6821
Content-Type: text/html

<data ahead>
```

#### What is the Conditional GET statement in HTTP? (limited discussion)
it is a get request which only fetches/gets the data if the condition is true.

---
# What are Cookies? (limited discussion)
We have learnt about Cookies in [[Internet Cookies\|Internet Cookies]]
Most of what a cookie is and what it can do has been covered there. 

Quoting from that file,

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/internet-cookies/#1" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



> A text file (`.txt`) which collects, stores and updates any stored session data for a particular unique website/web-domain and stores them locally on the device. 

</div></div>


---
# What is a Web Cache/Proxy Server?
Proxy Server is also called a Web Cache. It is a network entity that satisfies HTTP requests on the behalf of the original Web Server.

---
# EMAILs and SMTP - How does email work?
- Simple Mail Transfer Protocol (SMTP) is the principal application-layer protocol for Internet Electronic Mail. It uses the reliable data transfer service of TCP to transfer mail from the sender's mail server to the recipient's mail server. As with most application-layer protocols, SMTP has two sides: a client side which executes on the sender's mail server and a server side which executes on the receiver's mail server. 
- Both sides of SMTP are present on every mail server. When a mail server sends mail to other mail servers it acts as an SMTP client. When a mail server receives mail from other servers, it acts as an SMTP server.
- SMTP is much older than HTTP.
- It encodes all emails into 7-bit ASCII codes. SO Binary has to be converted to 7-bit ASCII for outgoing emails and vice-versa for incoming emails.
- This conversion adds to an overhead and creates compatibility issues with some of the other forms of communication.
- 7-bit capacity creates a problem that particularly large files cannot be transferred, sent or received via email.
## How are emails sent and received? (step-by-step)
1. Alice invokes her user agent for email, (GMail, Yahoomail etc.) provides Bob's email address, composes a message and clicks "send" button.
2. Mail moves to Alice's mail server, it is placed in a message queue (Alice's mail server has Alice's account, but not JUST her account, there are other people sending mails that are routed through the same server).
3. The Client side of Alice's server opens TCP connection with SMTP on Bob's mail server.
4. After Handshake, the SMTP client sends Alice's message into the TCP connection.
5. At Bob's end, the mail is received by SMTP server and places the email in his mailbox.
6. Bob can read the email whenever he feels like.
## SMTP format of messaging
Scan Page 150 of James F Kurose and slap it here.

---
# What is Domain Name Service (DNS)??
People prefer hostname identifier, while routers prefer fixed length, hierarchically structured IP addresses. In order to reconcile these preferences, we need a directory service that translates hostnames to IP addresses. this is the main task of the Domain Name System (DNS).
1. It is a distributed Database implemented in a hierarchy of DNS servers.
2. DNS is an application-layer protocol that allows hosts to query the distributed database. 
3. The DNS servers are often UNIX machines running Berkeley Internet Name Domain (BIND) software.
4. The DNS protocol runs over UDP and uses port 53.
5. It has hierarchal Directory Structure.
## Distributed, Hierarchal Database
- ***==Root DNS:==*** 13 original root servers. There are 1000 synchronus-roots now (for the rest of the world outside USA)
- ***==Top-level domain (TLD) servers==***:  servers dedicated to Domains such as .com, .net, .org, .edu, .gov etc. All countries have their own TLD... India has one for .in (for example)
- ***==Authoritative DNS servers==***: Every organisation or person (or anything in-between) needs it. they can either relegate Server space for it themselves or pay another company/organisation who do business around this (generally domain sellers do it) to do it for them. 
## How does DNS work?
![DNS Diagram.png](/img/user/Vaulted%20Images/DNS%20Diagram.png)
## What is the structure of DNS Resource Record?
![DNS Resource Record.png](/img/user/Vaulted%20Images/DNS%20Resource%20Record.png)

---
# Footnotes
1. Source: "Computer Networking: A Top Down Approach" - James F. Kurose et al. (J128 LRC Rack 4.67, Book 19421)

