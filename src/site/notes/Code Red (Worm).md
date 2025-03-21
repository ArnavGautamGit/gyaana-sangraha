---
{"dg-publish":true,"permalink":"/Code Red (Worm)/","tags":["CyberSec"]}
---


---
# Code Red (Worm)
On July 29, The US Federal Bureau of Investigation (FBI) proclaimed in a news release that " on July 19, the Code Red worm had infected more than 250k systems in 9 hours" which made it the World's fastest spreading [[Computer Worm\|worm]] in human history.

Code Red contained various forms of malicious code. It could also mutate from one form to another...
It uses a vulnerability on Microsoft Internet Information Serveer (IIS).
Code Red was a Chinese [[Computer Worm\|Computer Worm]] from 2001 which was easy to spot since it would deface websites. All attacked websites would have the following text:
```
HELLO!
Welcome to
https://www.worm.com !
Hacked by Chinese!
```

Code red activity was calendar based. 
Day 1 to 19, the worm spawned 99 threads that scanned for other vulnerable computers, starting at the smae IP address.
On Days 20 to 27, the worm launched a DDOS attack at the USA website of [The White House](https://www.whitehouse.gov). 
From Day 28 to end of the month, it did nothing.

It had multiple variants, the second variant was discovered in July 2001. It did not deface websites but propagation was randomised and far more optimised, the third variant discovered in August 2001 was significant re-write of the second. Although all variants were set to stop propagating in October 2002.

It worked by having a malicious copy of *explorer.exe* which it would place in (C:) drive so that the malicious copy is used not the original one.
Depending upon the worm, for 24 to 48 hours the program ran 300-600 threads (depending upon variant) to find other devices... after which it would force reboot the system - flushing out itself but leaving a backdoor and the Trojan Horse intact (which would be used to remotely access the pc and use it for DDOS attack)
Later versions used non-blocking sockets so that 1 thread does not slow down others and the worm can work faster and faster.

---
# Footnotes