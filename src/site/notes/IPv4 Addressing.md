---
{"dg-publish":true,"permalink":"/IPv4 Addressing/","tags":["Academics","CompNet"]}
---

# Index/Contents
[[IPv4 Addressing#What is IPv4 Addressing?\|#What is IPv4 Addressing?]]
[[IPv4 Addressing#What is Classful Addressing?\|#What is Classful Addressing?]]
[[IPv4 Addressing#What is Classless Addressing?\|#What is Classless Addressing?]]
[[IPv4 Addressing#Footnotes\|#Footnotes]]

-----
# What is IPv4 Addressing?
> ***Definition***: IPv4 Addressing is the method used  to uniquely identify different systems for global communication via Internet.
> ~ "TCP/IP Protocol Suite" - Behrouz A. Forouzan, Chapter 5, Page 114 of the Fourth Edition.

IPV4 address is a 32-bit address that uniquely & universally defines the connection of a host or router to the Intenet. It is the address of the interface.
Unique ---> Since each interface has a different one.
Universal ---> Since each person/organisation who wants to connect to the internet needs to adhere to this.

### IPv4 Address Space
IPv4 has an address space i.e., the total number of address used by the protocol. If a protocol uses b bits to define an address, the address space is $\large 2^b$ because each bit can have 2 values (0, 1)
Address space for 32 bits is $\large 2^{32}=4,29,49,67,296$ i.e., more than 4 billion but we are approaching this limit (the population approaching the double of 4 billion) and hence we are moving to [[IPv6\|IPv6]].

### IPv4 Notation
IPv4 can be notated in three ways:
1. ***Binary*** ---> Base 2, written in octets. (Octet = 8 and 8-bits = 1-byte, hence IPv4 is 4-byte)
2. ***Dotted Decimal*** ---> Base 256 (most common) when the octets are converted to decimal digits, they lie between 0 to 255.
3. ***Hexadecimal*** ---> Base 16 (least common) where the address has 8 digits, useful in network programming.

It is important to note that IPv4 addresses are stored in binary form inside computers.

### How to find Address Range when two IPv4 addresses are given?
The addresses must be in dotted decimal form for this to work.
If not, convert it to this notation.
1. Take the first byte of both the IP addresses, subtact them. Store as "a".
2. Take the second byte of both the IP addresses, subtract & store as "b".
3. Do the same for other two bytes and store them as "c" & "d".
4. Use the following formula to get Number of Addresses (Num): $$\Large Num = (a\times255^3 + b\times255^2 + c\times255^1 + d\times255^0)$$
### Operations on IPv4 Addresses (with shortcuts)
##### Bitwise NOT Operation
1. Convert to Binary, complement each bit.
2. If given IP is in Dotted Decimal, subtract each byte by 255

##### Bitwise AND Operation
1. Compare both IP addresses byte-by-byte.
2. If either number is 0 or 255, select the lower digit
3. If neither is 0 or 255, write each as sum of 8 terms, where each term is a power of 2. Select the lowest terms and add them to get answer.

##### Bitwise OR operation
1. Same as Bitwise AND, just select the higher number of the two this time when you compare them.

---
# What is Classful Addressing?
IP space is divided into five classes: A, B, C, D, E.
Classes were made to differentiate between different uses that IP may be used for. These "Classes" were very common back in the day but has been replaced by Classless in the mid-90s.

Class A has $\large 2^{31}$ addresses (50%), B has $\large 2^{30}$ addresses (25%), C has $\large 2^{29}$ addresses (12.5%) while the Classes D & E both have $\large 2^{28}$ addresses (6.5%) each.

## How are Classes Identified?
Classes are identified by their first few bits in Binary or their first byte if in Dotted Decimal. If Hexadecimal addresses are given, convert them to one of the two forms of Notation before moving forward:
![IPv4 Classful Addressing.png](/img/user/Vaulted%20Images/IPv4%20Classful%20Addressing.png)

## What are netid & hostid in IPv4?
All classes (except D & E) are divided into netid & hostid. These partts vary in length but they play a very important part in addresses. They are the IPv4 analogous of an office address and desk address. Where netid is used for creating office addresses,individual desks of individual employees/hosts are created using hostid.
![IPv4 Classful netid & hostid.png](/img/user/Vaulted%20Images/IPv4%20Classful%20netid%20&%20hostid.png)

## What are Blocks? What is their use?
Since only 1 byte in Class A defines the netid and inside that byte, only the Leftmost bit must be zero, other 7 bits can be used as "blocks" since they can be changed to create new IP Addresses.
It means, in Class A alone there can be 128 ($\large 2^7 = 128$) blocks out of which some may be reserved for special blocks.

***Blocks were assigned to organisations since they need their systems to be uniquely identifiable, it helps in finding the systems of a specific organisation easier. Also, each organisation can get their block registered, meaning maintaining records is easier***.

Each block contains 16,777,216 addresses ---> too many for an organisation.

Similarly for Class B, $\large 2^{16}$ blocks and 65,536 addresses in each block. Still too many...
For Class C, $\large 2^{21}$ blocks and 256 addresses in each block. Now they are too less for a large organisation! This is why classless addressing was derived.

***Notice how as we go down the classes, we get more and more number of blocks but less and less number of addresses, since as we go down the classes, the number of bits for netid increase, but the number of bits we can change for creating individual hostid decrease. ***

Number of Addresses in a block are found using: $$\Large N = 2^{(32-n)}$$
here, $\large N =$ Number of Addresses in each block
$\large n =$ Length of netid in bits.

To find first address, keep n leftmost bits & set the remaining bits ($\large 32-n$) to all 0s.
To find the last address, we keep n leftmost bits and set the other ($\large 32-n$) rightmost bits as all 1s.
Convert both to Dotted Decimal to get the answer. {[[IPv4 Addressing#^1a\|#^1a]]}

## What is a Network Mask (in Classful Addressing)?
The routers in the Internet use an algorithm to extract the network address from the destination address of a packet. To do this, we need a Network Mask {[[IPv4 Addressing#^1\|#^1]]}.
To extract the Network Address from the destination address of a packet, the router performs the AND operation on the destination address and the Network Mask.

---
# What is Classless Addressing?
Due to rapid growth of the population & hence rapid growth in Internet users, a short-term solution to compensate for the address space depletion, a new form of addressing with the same IPv4 is used to remove the class privilege. Since it removes classes altogether, it was called as "Classless Addressing" & it uses slashes instead, thus also seldom referred to as the "slash notation" or "Slash Addressing".

To replace classes, it used variable length blocks which may have any number of addresses per block - according to the needs of the client.
Theoretically, as long as the block length is in the power of 2, that can be a valid block length in Classless Addressing.
Organisations are granted a block of addresses of $\large 2^n$ where $\large n$ can be any number they want.

## Two-Level Addressing in Classless
In Classful Addressing, we used netid and hostid, in a similar way in Classless, we use the words ***prefix*** & ***suffix*** to denote the same. {[[IPv4 Addressing#^1b\|#^1b]]}

The notation changes in Classless Addressing, since the blocks are of variable length, we need to find the Network Mask and other things via the prefix length which is given in the IP Address and separated from it with a slash or CIDR (Classless Interdomain Routing).
![Slash Notation.png](/img/user/Vaulted%20Images/Slash%20Notation.png)

## How are Blocks allocated in Classless Addressing?
Classless Addressing was made to make it easier to assign blocks to ISPs (Internet Service Providers) and the organisation that assigns blocks to ISPs registered with them is [[Transport Layer#^1\|ICANN]] (it is the same organisation that assigns Port Numbers in the Transport Layer) 

For correct operation of CIDR or slash notatiuon, following three restrictions are needed:
1. Number of requested addresses need to be of power of 2
2. The value of prefix length (written with slash) can be found from the number of addresses i.e., $\large n = log_2(2^{32}/N) = 32 - n$
3. requested block needs to be allocated where there is a contiguous number of unallocated addresses in the address space. However, there is a restriction on choosing the beginning addresses of block - they must be divisible by the number of addresses in the block i.e., $\large X \times 2^{n-32}$ where $\large X=$ decimal value of prefix.



---
Next Chapter --->[[IP Classful Subnetting\|IP Classful Subnetting]]
# Footnotes
1. A ***Network Mask*** (also called a ***Default Mask***) in classful addressing is a 32-bit number with any $\large n$ leftmost bits all set to $\large 1$s and ($\large 32-n$) rightmost bits all set to $\large 0$s.
{ #1}

	1. In Classful adressing, for class A, value of $\large n=8$, for class B it is $\large n=16$ and for class C it is $\large n=24$
{ #1a}

	2. All the $\large 1$s of the Network Mask are called ***netid*** in classful addressing (or ***prefix*** in classless) while all $\large 0$s are called ***hostid*** in classful addressing (or ***suffix*** in classless)
{ #1b}


