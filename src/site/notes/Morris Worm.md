---
{"dg-publish":true,"permalink":"/Morris Worm/","tags":["CyberSec"]}
---


---
# Morris Worm
Also known as "Internet Worm of 1988".
Key things about the history of this Legendary Worm:
- One of the Oldest Worms distributed via the Internet (1988)
- Written by Robert Tappan Morris, a student of Cornell University
- Arrested in 1988 for the first felony comitted under the 1986 Computer Fraud and Abuse Act.
- Worm spread from the MIT campus instead.
- The Creator's father was a NSA cryptographer/agent at the time - Robert Morris
- The Creator of the worm - Robert Tappan Morris - later became a professor at MIT in 2006.

The worm exploited several vulnerabilities of targeted systems, including:
1. A hole in the debug mode of the UNIX sendmail program
2. A [buffer overflow](https://en.wikipedia.org/wiki/Buffer_overflow "Buffer overflow") or overrun hole in the finger network service
3. The transitive trust enabled by people setting up network logins with no password requirements via [remote execution](https://en.wikipedia.org/wiki/Berkeley_r-commands "Berkeley r-commands") (rexec) with [Remote Shell](https://en.wikipedia.org/wiki/Remote_Shell "Remote Shell") (rsh), termed rexec/rsh
4. The Worm also hit the users who worked with weak passwords. 

*Morris's exploits became generally obsolete due to decommissioning of Remote Shell (normally disabled on untrusted networks), fixes to sendmail and finger, widespread network filtering, and improved awareness of weak passwords.*

**Keynote:**
Although Morris said that he did not intend for the worm to be actively destructive, instead seeking to merely highlight the weaknesses present in many networks of the time, a consequence of Morris's coding resulted in the worm being more damaging and spreadable than originally planned. It was initially programmed to check each computer to determine if the infection was already present, but Morris believed that some [system administrators](https://en.wikipedia.org/wiki/System_administrator "System administrator") might counter this by instructing the computer to report a false positive. Instead, ==*he programmed the worm to copy itself only 14% of the time, regardless of the status of infection on the computer. This resulted in a computer potentially being infected multiple times, with each additional infection slowing the machine down to eventual unusability*.== This had the same effect as a [fork bomb](https://en.wikipedia.org/wiki/Fork_bomb "Fork bomb"), and crashed the computer several times.

---
# Footnotes