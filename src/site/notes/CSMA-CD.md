---
{"dg-publish":true,"permalink":"/CSMA-CD/","tags":["Academics","CompNet"]}
---


---
# CSMA with Collision Detection
In Carrier Sense Multiple Access with Collision Detection (CSMA/CD), collisions are detected by sensing the network's physical medium. Here's how it works:
1. A node wishing to transmit data first listens to the network medium (e.g., a shared cable or radio channel) to check if it is idle or busy.
2. If the medium is idle, the node begins transmitting its data. During transmission, the node also monitors the medium for any interference or increase in signal level.
3. If the node detects an increase in signal level above a certain threshold, this indicates that another node has begun transmitting simultaneously, causing a collision.
4. Upon detecting a collision, the node immediately stops transmitting and sends a short jamming signal to ensure all nodes are aware of the collision.
5. After the jamming signal, each node involved in the collision waits for a random amount of time (known as backoff time) before attempting to retransmit. This randomness helps prevent repeated collisions among the same set of nodes.

In CSMA/CD, collision detection is more direct than in Aloha or Slotted Aloha, where collisions are inferred based on the absence of acknowledgment from the receiver. In contrast, CSMA/CD allows nodes to actively detect collisions during transmission, resulting in improved channel utilization and reduced latency.


---
# Footnotes