---
date: 2024-12-12 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network]]"
---

# Firewalls

## Overview
- *What is it?*
  - a machanism that prevents unauthorised and unwanted communication over the networs
  - can be hardware, software or both
- *Why we use it?*
  - security
  - monitor traffic
  - access controll

## Packet filtering firewalls

- *Types*
  - *DROP*
    - accept only authorised traffic, drop eveything else
  - *ACCEPT*
    - accept everything except the unauthorised traffic

- *Rules are set bead on*:
  - source/destination ip
  - protocol used
  - source/destination port number
  - connection already established or not

## Iptables
### Chaning rules
![[Pasted image 20241212020150.png]]
### Chains "hook points"
![[Pasted image 20241212020307.png]]
