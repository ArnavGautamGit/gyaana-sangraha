---
{"dg-publish":true,"permalink":"/Transmission Control Protocol (TCP)/","tags":["CompSci","CompNet"]}
---


---
# Transmission Control Protocol (TCP)
> "A Protocol in the [[Transport Layer\|Transport Layer]] of [[Computer Networks\|Computer Networks]] which ensures reliable service between Application and Network Layers."

- Connection-Oriented Protocol
- Reliable Data Transfer is guaranteed i.e., no data will be lost.
- Explicitly defines Connection establishment, data transfer and connection teardown phases.
- ***==Checksum mandatory==***.
- Buffers for ***==Flow Controls are implemented as Circular Arrays==*** (Page 182, Fig 3.1, Forouzan)
- TCP offers ***==Full-Duplex Communication==*** i.e., Simultaneous Bidirectional Data Connection.
- TCP also offers Multiplexing and Demultiplexing (used for sending and receiving respectively) just like UDP.
- ### Message Format below: ![TCP Message Format.png](/img/user/Vaulted%20Images/TCP%20Message%20Format.png)
- Sequence Number and Acknowledgement number have been discussed already. {see highlighted portion of [[Transport Layer#^4\|Transport Layer#^4]] and [[Transport Layer#^6\|Transport Layer#^6]] to know more.}
- ***Reserved Bits***: Bits that are extra reserved to be given to Flags
- ***Flags*** (right next to the Reserved bits in the figure) are various flags for URG (Urgent), ACK (Acknowledgement), PSH (Push), RST (reset), SYN (Synchronize), FIN (Finish Connection).
- ***Window Size*** defines time to reply ACK. Must be obeyed in this case by TCP.


---
# Footnotes