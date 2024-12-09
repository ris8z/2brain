---
date: 2024-12-09 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network]]"
---

# Link State Routing Algorithm & Open Shortest Path First (OSPF)
 
## Link State Routing alogrithm

### Motivation
  - developed to address the slow convergence of Distance Vector Routing
  - store more network information using additional tables:
    - *Neighbour Table* tracks routers aviable for data exchange
    - *Topology Table* tracks all destination and every neighbour through which it can be reached.

### How it works?

#### 0) Key concept
- The idea is that *every node knows about everybody else*
  - (that differs from Distancd Vector where each node know just about thier neighbours)



#### 1) Neighbour discovry
```css
Node A -----nil----- Node B -----nil----- Node C
```
- On startup routers send and "hello" msg to all connected links.
- Recivers respond with their details
    - ip, subnetmask, etc.
    - which are stored in the *neighbour table*

#### 2) Measuring Link distance
```css
Node A -----10----- Node B -----05----- Node C
```
- Distance is either measured in *delay, bandwidth* or both
- Routers use spacial *echo packets* to get distance
- *if* load is to be consideresd:
  - time start when the packet is quequed
- *else*:
  - time start when the packet is sent
    
#### 3) Building Link State Adverstisements (LSAs)
```python
# LSA for A
Router ID: A
Sequence Number: 1
Neighbors:
  - Node B, Cost: 10

# LSA for B
Router ID: B
Sequence Number: 1
Neighbors:
  - Node A, Cost: 10
  - Node C, Cost: 5

#LSA for C
Router ID: C
Sequence Number: 1
Neighbors:
  - Node B, Cost: 5
```
- with all the info get from setps 1 and 2
- each node generate its LSA, that contains
  - *router ID*
  - *Neighbours* and their *distance*
  - Sequence Number *(SEQ)*
    - to ensure that only the last updates are processed.
  - *Age*
    - to ensure that packet dont keep moving around the network forever 
- LSAs are *generated periodically* or when *there is a change*

#### 4) Distributing LSAs
- LSAs are spreaded across the network using *flooding* (that is basically a BFS)
  - Routers farward *valid LSAs*
  - *invalid LSA* are dropped

#### 5) Constructing the Topology:
- Routers build a complete *network topology* from received LSAs
- Dijkstra’s Algorithm *computes the shortest path to all destination networks*

#### 6) Challenges:
- Large networks require *significant RAM*.
- *Router failures* may introduce incorrect routing information.

## Open Shortest Path First (OSPF)
### Overview
- type: *Link State Protocol* 
- layer: *layer 3 osi*, port 89
- it is *wildy use*

### How it works?
![[Pasted image 20241209035516.png]]
- **Autonums System (interior gateway protocol)** 
  - OSPF divides the network in parts called Autonmus System *AS*
  - Each *AS* is splitted into areas (*to speed up shortest path computation*)
- **AS Structure**
  - Each *AS* has a *backbone area (area 0)* and serverl other areas
  - *Routes* only knows the topology of their area
  - *Area border routers (ABRs)* they are mebers of more the 1 areas
    - they farward routing data between areas
  - *Autonomus system border routers (ASBRs)* connect the *AS* to the internet
- **Routes definitions**
  - *Intra-area*: routes within the same area
  - *Full inter-area*: routes between different areas
  - *External*: routes to the internet
- **Areas definitions** (block means that routing info are not advertised)
  - *Stub Area* (without ASBRs, i.e. 20, 30):
    - Blocks external routes; uses a default route for external destinations.
  - *Totally Stubby Area*:
    - Blocks both external and inter-area routes; uses only a default route.
  - *Not So Stubby Area* (with ASBRs):
    - Allows external routes from its own ASBR but blocks external routes learned from outside
- **Rules**
  - All routers in the backbone area should be directly connected
  - Routers in other areas can be indirectly connected
  - All areas should be connected to the backbone area
  - All inter-area communications must pass through the backbone area
  - There is no direct link between two non-backbone areas

### Challanges 
![[Pasted image 20241209042127.png]]
- For large networks, sharing the routing, info with all the routers in the network is an issue
  - Problem:
    -  *High routing overhead*
  - Solution:
    - Routers in every area can vote to make one router a *Designated Router (DR)*
    - Routers *send and receive* routing information *to and from* the *DR only*
    - Routers also select a *Backup Designated Router (BDR)* in case DR fails
  
