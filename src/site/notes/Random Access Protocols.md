---
{"dg-publish":true,"permalink":"/Random Access Protocols/","tags":["CompSci","CompNet"]}
---

# Index/Contents
[[Random Access Protocols#What are Random Access Protocols?\|#What are Random Access Protocols?]]
[[Random Access Protocols#Footnotes\|#Footnotes]]

-----
# What are Random Access Protocols?
Random Access Protocols are Protocols which are used to avoid the collision ([[Random Access Protocols#^1\|#^1]]) of data in a open connection when suddenly both sides of the connection wish to pass data at roughly the same time.

If any of the packets collide, those packets are considered destroyed i.e., packets cannot be reassembled due to certain packets missing i.e., the entire message needs to be resent.

The following protocols exist:
1. Aloha - both [[Pure Aloha\|Pure Aloha]] and [[Slotted Aloha\|Slotted Aloha]]
2. [[CSMA\|CSMA]]
3. [[CSMA-CD\|CSMA-CD]]
4. [[CSMA-CA\|CSMA-CA]]

---
Next Chapter --->[[Random Access Protocols#\|#]]
Previous Chapter --->[[Random Access Protocols#\|#]]
# Footnotes
1. Collision is a situation when two of the systems connected by a singular connection wish to send traffic on the same line - the traffic bits "collide" and the data is lost.
{ #1}


