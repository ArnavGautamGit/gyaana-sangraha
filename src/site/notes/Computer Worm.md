---
{"dg-publish":true,"permalink":"/Computer Worm/","tags":["Academics","CyberSec"]}
---


---
# Computer Worm
Worms are a type of Malware which does not need to attach itself to anything but could attach to files (rather than programs) and that too only for spreading itself. They spread exponentially faster than [[Computer Virus\|Viruses]]. Some Worms (called [[Clickjacking Worms\|Clickjacking Worms]]) can take over the PC/Phone and Click & Naviaget the UI on their own.

Some critical features of Worms:
1. Worms rely on spreading
2. Worm spreads as a standalone program
3. Can spread via a LAN, USB, CD, DVD etc... advance ones like Stuxnet can use Cloud Storage to spread.

---
## Worm Propagation Methods
Worms rely on spreading and they copy themselves and spread themselves faster than a Virus can (at least it is hoped that a good one should)
Some popular ways Worms of the past have spread:
- As attachments in email or instant-messaging apps.
- Devices that were used in Autorun mode (runs as soon as it connects, no need to get authorisation from user) like pendrives, CD, DVD, SD Cards etc.
- Remote Access Login Functionality can be used by the worm to spread.

They are best understood from Cast Studies such as [[Morris Worm\|Morris Worm]], [[Code Red (Worm)\|Code Red (Worm)]] and [[Stuxnet (Worm)\|Stuxnet (Worm)]] outbreaks.

---
## Mathematical Model of Worm Propagation
The Number of Infected Hosts will exponentially increase and Number of un-infected hosts will exponentially decrease. ![WPM.jpg](/img/user/Vaulted%20Images/WPM.jpg)
Keep in mind the following equation for to undertand WPMs better:
$$\large\dfrac{d}{dt}I(t) = \beta \times I(t) S(t)$$
See Also:
[[Worm vs Virus\|Worm vs Virus]]

---
# Footnotes

