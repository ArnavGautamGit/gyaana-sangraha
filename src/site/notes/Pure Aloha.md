---
{"dg-publish":true,"permalink":"/Pure Aloha/","tags":["CompSci","CompNet"]}
---


---
# Pure Aloha Random Access Protocol
A protocol where A & B are connected to each other & both want to send a message to each other, both of them by design on this protocol would send and listen for acknowledgement. As soon as either sender has anything to send, they will blindly start sending.

If no ACK received, then we know a collision occured & data was lost so both senders wait a random amount of time before retrying. 

***==Problem==***: If no data was being transferred, both of them will start sending at the same time and there will still be problems.

***==Throughput==***: 18.42%

---
# Footnotes