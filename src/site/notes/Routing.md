---
{"dg-publish":true,"permalink":"/Routing/","tags":["CompSci","CompNet"]}
---


---
# What is Routing?
***Routing*** is the process of selecting a path for traffic in a network or between or across multiple networks.
Routing can be of 4 kinds:
1. ***Unicast***: Using the unique port number of another router, we send a message to a specific device in a network.
2. ***[[Routing#^1\|Broadcast]]*** : delivers a message to all nodes in the network using a _one-to-all_ association; a single [datagram](https://en.wikipedia.org/wiki/Datagram "Datagram") (or [packet](https://en.wikipedia.org/wiki/Packet_(information_technology) "Packet (information technology)")) from one sender is routed to all of the possibly multiple endpoints associated with the [broadcast address](https://en.wikipedia.org/wiki/Broadcast_address "Broadcast address"). The network automatically replicates datagrams as needed to reach all the recipients within the scope of the broadcast, which is generally an entire network [subnet](https://en.wikipedia.org/wiki/Subnetwork "Subnetwork").
3. ***[[Routing#^2\|Multicast]]***: delivers a message to a group of nodes that have expressed interest in receiving the message using a _one-to-many-of-many_ or _many-to-many-of-many_ association; datagrams are routed simultaneously in a single transmission to many recipients. Multicast differs from broadcast in that the destination address designates a subset, not necessarily all, of the accessible nodes.
4. ***[[Routing#^3\|Anycast]]***: delivers a message to any one out of a group of nodes, typically the one nearest to the source using a *one-to-one-of-many* association where datagrams are routed to any single member of a group of potential receivers that are all identified by the same destination address. The routing algorithm selects the single receiver from the group based on which is the nearest according to some distance or cost measure.

Note: Many Indirect-Routing Algorithms using Djikstra's Algorithm (Shortest distance between two nodes) to implement. The section above is about Direct-Routing. 




---
# Footnotes
1. Wikipedia page on: [Broadcast](https://en.wikipedia.org/wiki/Broadcasting_(networking))
{ #1}

2. Wikipedia page on: [Multicast](https://en.wikipedia.org/wiki/Multicast "Multicast")
{ #2}

3. Wikipedia page on: [Network Socket](https://en.wikipedia.org/wiki/Network_socket)
{ #3}
