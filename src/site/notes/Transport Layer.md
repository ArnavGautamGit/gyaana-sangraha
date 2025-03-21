---
{"dg-publish":true,"permalink":"/Transport Layer/","tags":["CompSci","CompNet"]}
---

---
# Index/Contents
[[Transport Layer#What is Transport Layer?\|#What is Transport Layer?]]
[[Transport Layer#How do Port Numbers work?\|#How do Port Numbers work?]]
[[Transport Layer#How is Socket Addressing done?\|#How is Socket Addressing done?]]
[[Transport Layer#How is the data transported? (Pushing & Pulling)\|#How is the data transported? (Pushing & Pulling)]]
[[Transport Layer#What types of Controls are implemented on the Transport Layer?\|#What types of Controls are implemented on the Transport Layer?]]
[[Transport Layer#What is a Connectionless Service?\|#What is a Connectionless Service?]]
[[Transport Layer#What is a Connection-Oriented Service?\|#What is a Connection-Oriented Service?]]
[[Transport Layer#User Datagram Protocol (UDP)\|#User Datagram Protocol (UDP)]]
[[Transport Layer#Transmission Control Protocol (TCP)\|#Transmission Control Protocol (TCP)]]
[[Transport Layer#What are the mechanisms for implementing Flow Control & Congestion Control?\|#What are the mechanisms for implementing Flow Control & Congestion Control?]]
[[Transport Layer#What are TCP Timers?\|#What are TCP Timers?]]
[[Transport Layer#Footnotes\|#Footnotes]]

-----
# What is Transport Layer?
The Transport Layer is located between Application Layer and Network Layer. It provides service to the Application Layer and receives services by the Network Layer.

Regardless of the method used for Network Architecture used (see [[Application Layer#What are the known Network Application Architectures?\|Application Layer#What are the known Network Application Architectures?]]) we should know that the process to process communication happens via sockets.
This means that since each socket uses port numbers, we can say (by extension) that ***process-to-process communication occurs using addressing of port numbers***.

---
# How do Port Numbers work?
As we saw above, it is the port numbers that are used for running applications and allow addressing.
Port numbers are defined in 16 bits.
Using 16-bits we can define $\large 2^{16} = 65,535$ unique port numbers. these are divided into 3 parts:
1. ***==Well-Known Ports==***: Port Numbers 0 to 1,023 are a part of this range. They are assigned by ICANN {see [[Transport Layer#^1\|#^1]]}.
2. ***==Registered Ports==***: Port Numbers from 1,024 to 49,151 are reserved/registered with ICANN for specific services to avoid duplication with the well-known ones. 
3. ***==Dynamic/Ephemeral Ports==***: ranging from 49,152 to 65,535. They are used as temporary/private port numbers. Not registered anywhere.

ICANN assigns and controls Well-Known ports. It does not control, but still assigns Registered Ports but they neither control, nor assign Dynamic Ports.

***==Question==: How does the browser keep track of which packet is to be delivered to which window in modern computers?***
Browsers use Ephemeral Port numbers to keep track of the individual browser instance and tab. Hence, browser is able to send the appropriate packet to the appropriate tab/window. Having unique TCP connections for each browser tab/window also helps.

---
# How is the data transported? (Pushing & Pulling)
Delivery of items/packets from Sender to Receiver (or Producer to Consumer) happens in two ways:
1. ***Pulling***: Receiver sends request, Sender starts sending if it accepts.
2. ***Pushing***: Sender starts sending data as and when it is ready. Receiver controls how much data and at what rate the data is received using Flow Control. {see [[Transport Layer#^2\|#^2]]}

There is a need of flow control in pushing but not in pulling because the pull request is only sent for when the receiver is ready. Data can be pushed from many senders to many receivers at any time, needing Flow Control. 
Flow Control is popularly implemented using Buffer Queues in the routers and switches of a network (or any node packets use to "hop" off). {see [[Transport Layer#^3\|#^3]]}

---
# What types of Controls are implemented on the Transport Layer?
1. ***==Flow Control==***: Already Discussed above
2. ***==Error Control==***: Used to check and corrected errors in sending, receiving or reassembling packets/segments. It is generally implemented using individual Sequence Numbers assigned to each packet {see [[Transport Layer#^4\|#^4]] and [[Transport Layer#^5\|#^5]]} and we will also see the ACK Flag {[[Transport Layer#^6\|#^6]]} being used with it.
3. ***==Congestion Control==***: refer to the mechanisms and techniques that control the congestion and keeps the load below the capacity {see [[Transport Layer#^7\|#^7]] and [[Transport Layer#^8\|#^8]]}.

---
# What is a Connectionless Service?
The packets are sent from the sender to the receiver. There is no flow control, error control or congestion control in the network.
The messages can arrive out of order, and since they are not numbered, the receiver won't know that they are not ordered. For the same reason, the data can be lost (due to packet loss) and neither parties will know. The Receiver does not even know if the sender has sent all the files or if the file sending is still on-going...
All in all, coordination is present between sender and receiver.
![Connectionless Service.png](/img/user/Vaulted%20Images/Connectionless%20Service.png)

---
# What is a Connection-Oriented Service?
Data exchange can only happen after establishing a connnection. All Packets have a sequence number and nothing can occur without requests. There is numbering, and receiver knows exactly how much data is transferred. The data that arrives earlier than the data that should have preceeded it is kept on hold until the preceeding data is received.
![Connection-Oriented Service.png](/img/user/Vaulted%20Images/Connection-Oriented%20Service.png)

---
# Establishing Connection demonstratated using some  Finite State Automata
Concept can be better understood using Finite State Machines (FSM) in Automata Theory
![Connection Services as FSM.png](/img/user/Vaulted%20Images/Connection%20Services%20as%20FSM.png)

---
# User Datagram Protocol (UDP)
- Very Simple Connectionless Protocol using minimum overhead.
- Unreliable Data Transfer (packet loss, delay, in-ordered receiving all possible)
- IP + [[Inter-Process Communication\|Inter-Process Communication]]
- ### Message Format 
	- Packets transferred by UDP are called User Datagrams
	- These datagrams have ***fixed header size of 8 bytes*** (made of 4 fields of 2 bytes each)
	- 2 bytes = 16 bits.
	- The first two fields are source and destination address. The other two fields define the total length of the UDP datagram and the optional checksum respectively.
	- Although the Message can carry upto 65,535 bytes of data, we have to keep in mind that the ==$\large UDP \ Datagram \ Size = 65,535 - 8 \ (UDP \ header) - IP \ Packet \ Size$==
	- if we include the header in size, we get ==$\large UDP \ Datagram \ Size = 65,535 - IP \ Packet \ Size$==
	- The Message Format from the book is pasted below ![UDP Message Format.png](/img/user/Vaulted%20Images/UDP%20Message%20Format.png)
	- Our College being the pain the ass that they are, would give us questions to decode the Hexadecimal to Binary to find the fields in the header above.
	- ***==Example==***: CB84000D001C001C is the hexadecimal UDP header, find the source port number, destination port number, total length, total data length (excluding the header), direction of packet flow and name of client process.
		- First 4 Hex codes give us the source port, 
		- the next 4 give us the destination port, 
		- third 4 give us the total length. 
		- Total Length - 8 = Data Length.
		- destination port is 13 (here) which lies in range of 0-1023, hence it is a well known port, hence the direction is from client towards server.
	- No Flow Control is available in UDP.
	- No Error Control except Checksum. (Checksum itself is optional)
	- No Congestion Control either.
- ### Checksum
	- Checksum is never all 1s.
	- Checksum is sent as All 0s with 1s complement value of all 1s.
	- If there is a data loss, then the value of checksum on the receiver side will change. It will not be all 0s after 1s complement. 

---
# Transmission Control Protocol (TCP)
- [[Application Layer#What is TCP? Basics of TCP\|Application Layer#What is TCP? Basics of TCP]]
- Connection-Oriented Protocol
- Reliable Data Transfer is guaranteed
- Explicitly defines Connection establishment, data transfer and connection teardown phases.
- ***==Checksum mandatory==***.
- Buffers for ***==Flow Controls are implemented as Circular Arrays==*** (Page 182, Fig 3.1, Forouzan)
- TCP offers ***==Full-Duplex Communication==*** i.e., Simultaneous Bidirectional Data Connection.
- TCP also offers Multiplexing and Demultiplexing (used for sending and receiving respectively) just like UDP.
- ### Message Format below: ![TCP Message Format.png](/img/user/Vaulted%20Images/TCP%20Message%20Format.png)
- Sequence Number and Acknowledgement number have been discussed already. {see highlighted portion of [[Transport Layer#^4\|#^4]] and [[Transport Layer#^6\|#^6]] to know more.}
- ***Reserved Bits***: Bits that are extra reserved to be given to Flags
- ***Flags*** (right next to the Reserved bits in the figure) are various flags for URG (Urgent), ACK (Acknowledgement), PSH (Push), RST (reset), SYN (Synchronize), FIN (Finish Connection).
- ***Window Size*** defines time to reply ACK. Must be obeyed in this case by TCP.

Learn More in [[Transmission Control Protocol (TCP)\|Transmission Control Protocol (TCP)]]

---
# What are the mechanisms for implementing Flow Control & Congestion Control?
## Flow Control Mechanisms
Flow Control is controlled using Sliding Window Protoocol where the receiver's sliding window is used to control the speed of transmission of packets from sender to receiver altering & controling the network flow.

> ***==Note==***: 
> The total number of sequence numbers will be $\large 2^m$ $\large where, \ m = size \ of \ sequence \ number \ field \ in \ bits$.
> The Maximum Window size is then $\large 2^m -1$ 

The following three mechanisms exist:
1. Stop & Wait
2. Go-back-N
3. Selective Repeat
### Stop & Wait Mechanism
- Connection-Oriented Protocol which uses both Flow & Error Control.
- Both sender and receiver use sliding window of size 1. Once a packet is received by receiver, it sends an ACK to sender.
- Without ACK of previous packet, sender does not send next packet.
- Every Packet has a Checksum in header to check for corrupted packets.
- If receiver finds Checksum as Incorrect, it will silently discard the packet.
- Sender also uses a timer of its own. If the timer runs out and no ACK is received, it resends the packet assuming it was corrupted or lost. Hence, Sender needs to hold a copy of the packet until ACK number arrives i.e., expect slight overhead.
#### Pros
- ***Cheap & Simple to implement*** ---> Easiest and Simplest of all mechanisms. Can be implmented with just 2 sequence numbers (0 and 1) if needed. Since the Maximum Window Size is $\large (2^m - 1) =1 \ for \ m=1$ 

#### Cons
- ***No Pipelining or Efficiency*** ---> Channel is empty for the time when ACK is expected (i.e., empty for 50% of the time). This makes it a highly inefficient mechanism for thick and long channels. {see [[Transport Layer#^9\|#^9]]}
- ***Very Slow*** ---> High Waiting Time.
- ***Duplicate Packets*** ---> If the ACK to a particular file is lost or corrupted, it will lead to the packet being resent after timeout creating Duplicate Packets which may or may not be silently discarded.
### Go-Back-N, Selective Repeat & Silly Window Syndrome
![Flow Control Mechanisms.png](/img/user/Vaulted%20Images/Flow%20Control%20Mechanisms.png)
![Flow Control Mechanisms - 2.png](/img/user/Vaulted%20Images/Flow%20Control%20Mechanisms%20-%202.png)

## Congestion Control Mechanisms
There exist two mechanisms to control Congestion:
1. Additive Increase
2. Slow Start Algorithm

Study both of them from slides for better in-depth understanding but the notes are scanned and placed here nevertheless.
![Congestion Control Mechanisms.png](/img/user/Vaulted%20Images/Congestion%20Control%20Mechanisms.png)

---
# What are TCP Timers?
To perform their operations smoothly, most TCP implementations use at least 4 timers:
1. Retransmission
2. Persistence
3. keepalive
4. TIME-WAIT

## Retransmission Timer
- handles retransmission time-out (RTO) {see [[Transport Layer#^10\|#^10]]}.
- There are certain rules of the RTO:
	- When TCP sends the segment in front of the sending queue, it starts the timer.
	- When the timer expires, TCP resends the first segment in front of the queue and restarts the timer.
	- When a segment or segments are cummulatively acknowledged, the segment or segments are purged from the queue.
	- If the queue is empty, TCP stops timer, otherwise it restarts the timer.
- #### Calculating RTT & RTO
	- To calculate $\large RTO$ we need to first calculate RTT (Round Trip TIme) which are of 2 types, $\large RTT_M$ (Measured RTT) and $\large RTT_S$ (Smoothed RTT)
		- $RTT_M =$ Instantaneous RTT measured for a particular packet.
		- $RTT_S =$ Average of many $RTT_M$
			$\large Updated \ RTT_S = (1-\alpha)\times RTT_S + \alpha\times RTT_M$ 
			$generally, \alpha = \dfrac{1}{8}$
		- $\large RTT \ Deviation \ i.e., \ RTT_D = \dfrac{RTT_M}{2}$ ***==For First Value==***
		- $\large RTT_D = (1-\beta)\cdot RTT_D + \beta \times | RTT_S - RTT_M |$ ***==for subsequent values==*** 
			  $generally, \ \beta=\dfrac{1}{4}$
		- $\large RTO = RTT_S + 4 \times RTT_D$

## Persistence Timer
A timer used to correct deadlocks when two TCP timers are waiting for each other to respond.
Persistence Timer is started by the sender which sends a 1 byte probe when the timer ends. The 1 byte probe is a request to the receiver to resend acknowledgement. This breaks the deadlock.

## keepalive Timer
There to prevent a long idle connection between two TCPs. If (say) the client crashed, the connnection remains open forever. The keepalive timer resets its timer everytime it hears from the receiver. The time-out is usually two hours.
If server hears nothing for 2 hours, it sends a probe segment. If probe is not responded to, multiple probes are sent 75 seconds apart. Connection is terminated after 10 probes are not responded to.

## TIME-WAIT Timer
Not understood well. Need Ma'am's help to understand.
Most likely not in syllabus.
***==Update: nahi aaya T2 mein lol==***.

---

Next Chapter --->[[Network Layer\|Network Layer]]
# Footnotes
1. ***International Corporation of Assigned Names and Numbers***. Governing body over port number addressing among other things. [Their Website](https://www.icann.org) and their address is 4676 Admiralty Way, Suite 330 Marina del Rey, CA (Phone: 90292-6601)
{ #1}

2. ***Flow Control*** is a process to control the rate at which the sender sends data and the receiver receives data so that there is no bottleneck or packet drops on either side of the connection. It is popularly implemented using Buffers.
{ #2}

3. A ***Buffer*** is a set of memory locations that can hold packets at the end it is placed. It is applied on Sender and Receiver ends for Flow Control.
{ #3}

4. ***==Sequence Numbers are specific numbers assigned to the first bit of data contained in the packets/segments to track the sequence of packets sent/received.==*** If one of the packets is corrupted/lost, it is easier for the sending program to send JUST the missing packet instead of the entire file again. It also allows the receiver to detect duplicates if two packets have the same sequence number.
{ #4}

5. Also, keep in mind that Sequence Numbers have a limit of size denoted by the number of bits that are permissible in the header. For example, if 4 bits are permitted in HLEN (Header Length), then only sequence numbers from 0 to 15 are allowed. Sometimes these finite bits also include stuff apart from Sequence Numbers which is why there is a provision of Reserve Bits!
{ #5}

6. ***ACK (Acknowledgement) Flag*** is the Flag used by the receiver that it has received the packets sent by the sender. ACK Flag are included with any other flags in the Header of the ACK Flag packet sent by the receiver to the sender telling them its all okay. If ACK is to be sent for each packet, then the ACK packets will have their own Acknowledgement Number. ***==Acknowledgement Number is the byte number that the receiver of the segment is expecting to receive from the other party.==*** Sender starts a timer everythime it sends a packet, if the ACK for it does not arrive in time, it is resent. Duplicate packets can be discarded by the receiver silently and inordered packets can be discarded or stored until missing ones arrive. We will also learn about how the ACK Flag is used in TCP only for acknowledgement in the context of any connection requests.
{ #6}

7. ***Load*** is defined as the number of packets on the network. While capacity is the maximum load the network can take.
{ #7}

8. ***Congestion*** is the situation where load is greater than the capacity.
{ #8}

9. ***Thick and Long Channels*** refer to Network Channels which have a large bandwidth and high Round Trip Delays. By the same logic, Narrow and Short channels are low bandwidth, low RTD channels.
{ #9}

10. ***Retransmission time-out*** refers to the waiting time for an acknowledgement of a segment.
{ #10}
