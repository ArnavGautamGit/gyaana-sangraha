---
{"dg-publish":true,"permalink":"/IP Classless Subnetting/","tags":["CompNet","Academics"]}
---


---
# IP Classless Subnetting
> "***Subnetting*** is process of dividing a network into smaller subnetworks (called  as ***Subnets***) with each subnetwork having its own subnetwork address."
> ~ TCP/IP Protocol Suite (4th Edition), Page 132.

### Why use Subnets?
Same Reasoning as given in [[IP Classful Subnetting#Why use Subnets?\|IP Classful Subnetting#Why use Subnets?]]

### Pre-requisites to know
Same as [[IP Classful Subnetting#Pre-requisites to know\|IP Classful Subnetting#Pre-requisites to know]] 

### How are subnets made?
- The total number of addresses given to the organisation are $\large N$ 
- The prefix length of each address in the main network is $\large n$
- The addresses asssigned to each subnet is $\large N_{sub}$
- The prefix length of each address in the subnet is $\large n_{sub}$
- The number of subnets is $\large S$.
- The formula for prefix length of subnet is: $$\Large n_{sub} = n + log_2 \ (\dfrac{N}{N_{sub}})$$
- The number of addresses in each subnetwork should be a power of 2
- The starting address in each subnetwork should be divisible by the number of addresses in that subnet. This can be achieved if we first assign numbers to arge subnets.
### Finding Information about each subnet
- 

---
# Footnotes