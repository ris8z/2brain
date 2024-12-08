---
date: 2024-12-08 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network]]"
---

# Distance vector routing and Router Information Protocol

## What is it?
- an algorithm used in Router Protocl (to build routing table)
  - *distance* means how far
    - can be in terms of hops, delay etc.
  - *Vector*  means direction
- Each router knows the distance to its directly connected neighbors
- Each router *update* each other on a *fixed interval*
- It uses Hop Count
- Very good for small network



## How it works?
![[Pasted image 20241208183424.png]]
- *start* 
  - every routers has only their directly neighbours
  - in their routing table, with *Hop Count = 0*

![[Pasted image 20241208183956.png]]
- *after a while*
  - these routing table will be exchaned between the 4 routers
  - every router will update their routing table
  - NOTE each time you go trough a router the Hop Count += 1
- *IMPORTANT*
  - while routers are building their routing table
  - no data can flow :0

## Count to infinity Problem
![[Pasted image 20241208190339.png]]
- Assume this network of routers for example

![[Pasted image 20241208191148.png]]
- if the link between *B* and *D* goes down
    - B routing table
      - So *B* update *D* value *from 15 -> Undefined*

![[Pasted image 20241208191534.png]]
- In the next *Iteration of boradcasting* routing tables
  - B tells to A that D is unreachable
    - So *A* update *D* value *from 22 -> Undefined*
  - A tells to B that D is just 22 hop away
    - So *B* updates *D* value *from Undefined -> 22 + 7 = 29*
- Creating a loop that icrease D distance up to infinty

## Routing Information Protocol (RIP)

### Overview
- type: *Distance vector routing Protocol*
- layer: *Application* layer, uses *UDP* port 520
- funcionality:
  - sends complete RT to neighbours *every 30s*
  - use hop count to find the best path (max 15 to avoid loops)
  - infficent for large networks

### RIP versions
- v1
  - support *only classful routing*
  - uses *boradcast* for route updates
  - *No secuirity*
- v2
  - support *VLSM*(subnetmask info sent with routes)
  - uses *multi-cast* for update
  - *Router Authentication*

### Challenges and solution
- Invalid routes (can say in routing table for sevarl minutes, *sending traffic to black holes*)
  - solution
    - if a link goes down, send an *instant update*
- Count to infinity problem:
  - solutions
    - *max hop count*: 15
    - *Split horizion*: Do not advertise routes back to the source router
 
