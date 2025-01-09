---
{"dg-publish":true,"permalink":"/Layers of Computer Networks/","tags":["Academics","CompNet"]}
---


---
# Layers of Computer Networks
1. ***==Application Layer==***: The top layer where the network apps and their application-layer-protocols exist. In the iunternet's case protocols like HTTP and FTP reside here. Packets are referred to as ***messages*** in this layer.
2. ***==Transport Layer==***: Transports application-layer messages between application endpoints. Internet's TCP and UDP reside here. Transport-layer Packets are called as ***segments***.
3. ***==Network Layer==***: Delivers a segment (broken into Network-layer packets called ***Datagrams***) from the Transport layer of the sender to the Transport layer of receiver.
4. ***==Link Layer==***: Also called Data Link Layer. Network-layer Datagram is delivered from sender node to receiver node's Network Layer.
5. ***==Physical Layer==***: Job of this layer is to move the individual bits within the frame from one node to the next. Protocols in this layer are physical layer protocols that depend on the transmission medium like Ethernet, Optical Fiber etc.

---
Next Chapter ---> [[Application Layer\|Application Layer]] 
# Footnotes


