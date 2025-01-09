---
{"dg-publish":true,"permalink":"/hping/","tags":["Academics","CyberSec","CompNet","EthHack"]}
---


---
# hping
> hping is a network tool in order to create or generate network packets in order to test network, service, or system performance. Sometimes (by [[Hackers\|Hackers]]) these packets are actually used to scan [[Computer Networks\|Computer Networks]] and Systems.

It is an old tool - there are newer versions like hping2 and hping3 that have been developed.
It has its own commands that one will have to run.

### Commands
```sh
# ICMP Ping
hping3 -1 <IP Address>
hping3 -c 3 <IP Address> # will limit number of pings to 3
```

```sh
# ACK scan: used when host does not reply to ping
hping3 -A <IP Address> -p <Port Number>
hping3 --ack <IP Address> -p <Port Number>
```

```bash
# UDP scan: No response if port is open & "ICMP unreachable" if closed.
hping3 -2 <IP Address> -p <Port Number>
hping3 --udp <IP Address> -p <Port Number>
```

```sh
# FIN, PUSH, URG Scan
hping3 -F -P -U <IP Address> -p <Port Number>
```

```sh
# Find Initial Sequence Number
hping3 <IP Address> -Q -p <Port Number> -s
```

```sh
# Firewalls drop TCP packets with timestamps.
hping3 -S <IP Address> -p <Port Number> --tcp-timestamp
```

```sh
#SYN Scan
hping3 -8 <Port Number Range> -S <IP Address> -V
```

```sh
# SYN Flooding
hping3 -S <First Network IP> -a <Last Network IP> -p <Port Number> --flood
```

```bash
# Scan entire Subnet for live hosts
hping3 -1 1.1.1.x --rand-dest -I eth0 
# randomly replies to ICMP requests among all live hosts from 1.1.1.1 to 1.1.1.255 that are connected to the interface eth0.
```


---
# Footnotes