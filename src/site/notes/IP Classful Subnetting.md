---
{"dg-publish":true,"permalink":"/IP Classful Subnetting/","tags":["#CompNet","Academics"]}
---


---
# IP Classful Subnetting
> "***Subnetting*** is process of dividing a network into smaller subnetworks (called  as ***Subnets***) with each subnetwork having its own subnetwork address."
> ~ TCP/IP Protocol Suite (4th Edition), Page 132.

### Why use Subnets?
We know that in Classful Addressing, there are various classes from A to D. In Classes A & B, we have many IP addresses per block which are too big. In classes C & D, the number of blocks are great but not enough addresses per block.

Best idea is to use subnetworkd to get as many blocks and addresses you need! It is dependent on the company/organisation's needs more than anything else!

### Pre-requisites to know
- ***==Subnet Mask==***: Just like a [[IPv4 Addressing#What is a Network Mask (in Classful Addressing)?\|Network Mask]] (also called: Default Mask) is needed for every network, we need to create subnet masks which will act as the default masks for the individual subnets. In classful addressing, it will create a subnetid and hostid.
- ***==Changes in Length==***: Subnetting will increase the length of the netid and reduce the length of the hostid. If $\large S$ subnets are made, (given that the variable $\large S$ is in the power of 2) the subnetid (prefix length) for each network is: $$\Large n_{sub} = n + log_2S$$
### How are subnets made?
- Since Classful Addressing is a special case of Classful Addressing, The subnetting procedure & design is same as: [[IP Classless Subnetting\|IP Classless Subnetting]]


---
# Footnotes