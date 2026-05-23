---
{"dg-publish":true,"permalink":"/NOSTR/","tags":["CompNet","CyberSec"]}
---


---
# NOSTR
> NOSTR or "Notes and Other stuff Transmitted via Relays" is effectively a [[Computer Networking Protocols\|Network Protocol]] that allows to share notes or anything else (most often used for social media) by using your [[Web Sockets\|Web Sockets]] with [[Asymmetric Key Encryption\|Asymmetric Key Encryption]] for account security. 

It effectively creates a [[Decentralised Network\|Decentralised Network]] without using [[Blockchain\|Blockchain]] for anything except payments like Zaps. It is an alternative technology to Blockchain created by Jack Dorsey who has previously also created Twitter but Nostr is not meant to kill Blockchain, rather support it.

Similarly, another protocol named [[AT Protocol\|AT Protocol]] was made to host [[Bluesky\|Bluesky]] - another alternative to X. I personally do not know much about Bluesky since I am not interested on how it is made but I use both.

### Account Creation & Logins
Just like in [[Asymmetric Key Encryption\|Asymmetric Key Encryption]], there is a concept of Public & Private Key here as well. Public Key is akin to your user ID which is unique to you while your Private Key is used to authenticate you similar to a password. This effectively means that your username can change but your Public Key cannot.

### How it works
Nostr gives the user two keys - a Public Key that can be shared with anyone alongside a Private Key that the user keeps secret. This private key must be used to sign your messages or any other content you put out on the network and works the same way it does in existing technologies like [[Digital Signatures\|Digital Signatures]].

Since Nostr is a protocol and part of the back-end of decentralised infrastructure - there are various apps for various usecases that can utilise the network. Each app is created by creating a user-facing client which interfaces with the backend protocol (Nostr). So all apps built on Nostr can be used with the same Key pair meaning one account for all apps! 

### Censorship Protection
Since your Account is decentralised, you cannot be censored or de-platformed.
This censorship resistance is driving people to use it in the first place over regular social media which features a centralised control from the company behind the social media and the company itself can de-platform any user or can be pressured into de-platforming a particular user by either a government that has the most users (controlling their revenue) or the government where the company is based (controlling their freedom).

### Zaps
Zaps are a way of supporting creators monetarily, they are paid in [[Satoshi (SAT)\|Satoshi (SAT)]] which is the smallest unit of [[Bitcoin (BTC)\|Bitcoin (BTC)]]. Zaps cannot be paid with regular on-chain BTC, it needs wallets based on the [[Lightning Network (LN)\|Lightning Network (LN)]] to ensure high speed of payments & low charges on payments. Apart from Bitcoin and Zaps - Nostr is free and independent of Bitcoin and [[Blockchain\|Blockchain]] Technology as a whole.

### Clients
Many different clients have been made on Nostr including [[Primal (App)\|Primal (App)]] where I made an account on 7th December 2025. My Public Key has been recovered!

People only focus on social media clients that utilise Nostr instead of clients such as [[Satlantis\|Satlantis]] or [[Highlighter Nostr Client\|Highlighter]]. You can have backups & other such things.

---
# Footnotes