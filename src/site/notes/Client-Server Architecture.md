---
{"dg-publish":true,"permalink":"/Client-Server Architecture/","tags":["Academics","CompNet"]}
---


---
# Client-Server Architecture
> A type of [[Network Application Architecture\|Network Application Architecture]] which employs multiple clients being served any queried data by the server. It is one of the most common architectures employed in [[Computer Networks\|Networks]]. 

Applications hosted on a server can also be called "Server Applications" instead of Network Applications. Client Server Architecture also requires its own protocols such as [[Dynamic Host Configuration Protocol (DHCP)\|DHCP]] and [[HyperText Transfer Protocol (HTTP)\|HTTP]] to function.

In the context of the Internet, since the internet is a network connecting various networks and the websites are like applications hosted on this network, it is important that hosted Internet Applications (Websites) be assigned unique addresses, but memorable domain names. [[Domain Name Service (DNS)\|Domain Name Service (DNS)]] is a protocol used to map unique domains with the unique domain names and humans do not have to memorise their [[IPv4 Addressing\|IPv4 Addressing]].

These servers are protected from [[DOS Attack\|DOS Attack]] and [[DDOS Attack\|DDOS Attack]] by using [[Proxy Servers\|Proxy Servers]].

| ***CLIENTS***                                                                                | ***SERVER***                                              |
| -------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| Communicates with Server.                                                                    | Host that is in Always-on mode.                           |
| May have different IP addresses due to [[Dynamic Host Configuration Protocol (DHCP)\|DHCP]]. | Server IP Address is permanently the same forever.        |
| Clients cannot communicate with other clients.                                               | [[Server Farms\|Server Farms]] offer an unmatched scalability potential |

---
# Footnotes
1. Source: "Computer Networking: A Top Down Approach" - James F. Kurose et al. (J128 LRC Rack 4.67, Book 19421)