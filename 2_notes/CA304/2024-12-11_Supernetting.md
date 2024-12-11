---
date: 2024-12-11 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network 2]]"
---

# Supernetting

## Overview
- Make *bigger network* from small ones
- To make a bigger network we need more host
  - So we borrow bits from the NETID
- The main *goal* of this is *reduce the size of routing table*

## Rules

- Make sure *networks* are *contiguous*
  - Good: 192.168.0.0, 192.168.1.0, 192.168.2.0, 192.168.3.0
  - Bad!: 192.168.10.0, 192.168.40.0, 192.168.55.0, 192.168.67.0

- N of networks to join must be a *power of 2*

- The value of the *first non common byte* must be either
  - 0
  - Multiple of the number of networks to be aggregated

## How?
![[Pasted image 20241211210738.png]]
- I.E. Let’s aggregate *192.168.0.0/24* and *192.168.1.0/24*
- Aggregate networks by:
  - Setting the *common bits* to *1* and setting the *remaining bits to 0* (xnor)
- The *supernet IP* address will be the *address of the 1st network* in the list (192.168.0.0) 
- With the *new subnet* mask 255.255.254.0 or /23
