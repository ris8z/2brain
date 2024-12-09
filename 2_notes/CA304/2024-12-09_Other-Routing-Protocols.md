---
date: 2024-12-09 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network]]"
---

# Other Routing Protocols

## Enhanced Interior Gateway Routing Protocol (EIGRP)
- **Layer 3 Protocol:** Protocol ID 88.
- **Origins:**
  - Initially Cisco proprietary.
  - Now an open standard.
- **Type:** Hybrid interior gateway protocol (combines characteristics of distance-vector and link-state protocols).
- **Key Features:**
  - Sends distance-vector updates with network information and distances.
  - Builds neighbor and topology tables.
  - Sends routing updates only on topology changes.
  - Uses **Hello messages** to maintain router-neighbor relationships.
  - Multicast is used for routing updates.
- **Metrics:**
  - Uses 5 "K" constants: **Bandwidth**, **Delay**, **Load**, **Reliability**, **MTU**.
  - Default metrics: Bandwidth + Delay.
  - Selects routes with the lowest cumulative metric.
- **Other Features:**
  - Supports **load balancing** across paths.
  - Fast convergence (within seconds).
  - Uses the concept of **Autonomous Systems (AS):**
    - Routers must know their AS.
    - Border routers connecting multiple AS can belong to multiple AS.


## Border Gateway Protocol (BGP)

- **Layer 7 Protocol:**
  - Uses **unicast** over **TCP port 179**.
- **Type:** Exterior Gateway Protocol.
- **Purpose:** Routes between Autonomous Systems (AS).
- **Internet Role:**
  - The only protocol used for Internet routing.
  - Commonly used between ISPs.
- **Key Features:**
  - **Path Vector Protocol:** A variation of distance-vector routing.
  - Views an entire AS as a single hop.
  - **BGP Peers:** Routers are manually configured for communication.
- **Best Path Selection Criteria:**
  - Weight of the interface.
  - Source of the path.
  - Path length.
  - Preferred path or AS entry point.
- **Challenges:**
  - The most complex routing protocol to implement.
  - Slow convergence by default.
  - Misconfigurations can turn private networks into public "transit networks" between ISPs.
- **Focus:**
  - Designed with a strong emphasis on **security** and **scalability**.
