---
date: 2024-12-11 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network]]"
---

# Subnetting

## Broadcast domain
- Is a network where each divce can reach another one with a broadcast request
- They are limited by  the router
  - because router do not farward broadcast

## Large Brodcast domain
- A network with a lot of host
- due too each host can broadcast
  - slow down network operetion
    - networks must handle a lot of brodcaset request
  - slow down device operetion
    - each device must handle a lot of broadcaste request

## How to Fix? Subnetting
- We fix this problem with subnetting
- we *borrow bits* from the *hostid* to create
  - *more networks*
  - *with less hosts*
