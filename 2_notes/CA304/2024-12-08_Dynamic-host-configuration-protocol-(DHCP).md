---
date: 2024-12-08 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network 2]]"
---

# Dynamic host configuration protocol (DHCP)

## What it does?
it lease *private address* to each host

## Who does it?
the *DHCP server* that can be the *router*

## How it does it?
![[Pasted image 20241208164823.png]]
- *Host* send a *DHCP discover*
  - that contains (host name, mac address)
- *DHCP server* respond with a *DHCP offer*
  - that contains (ip adress, netmask, default getway) not in use

![[Pasted image 20241208164924.png]]
- *Host* send a *DHCP request*
  - that contains (the ip and getway that it got)
- *DHCP server* send a *DHCP ack*
  - that end the contract for the *ip address lease*

## How much time it last?
- default *lease time is 1 day*
- then the host need to *renewit*

## DHCP addresss allocation types
* *Dinamic*
  - hosts are give address from a pool random
* *Automatic*
  - hosts are give the previous address if not in use
* *Static*
  - host have an reserved ip linked to their MAC address
