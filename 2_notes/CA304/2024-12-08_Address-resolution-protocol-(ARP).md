---
date: 2024-12-08 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network]]"
---

# Address resolution protocol (ARP)

## what it does?
Allow to get the *MAC* address fromt the *Ip* address of an host
So we can use the Ethrent protocl

## How it does it?

### Same network
![[Pasted image 20241208155622.png]]
- The *source* bordcast and *ARP request* (with ip address of destination)
- *Whoever* get the request:
  ```python
  if arp_request.ip_destination == MY_IP:
      send(arp_replay(MY_MAC))
  else:
      pass
  ```
### Different newrok
![[Pasted image 20241208160246.png]]
- The *source* bordcast and *ARP request* (with ip address of destination)
- The *router*:
  ```python
  if arp_request.ip_destination in SubNetB:
      send(arp_replay(MY_MAC)) # gli manda il mac suo del router
      send(arp_request(ip_destination, SubNetB)) # ottiene il mac di D e se lo salva 
  else:
      pass
  ```
- This is *Proxy ARP* (bc router do not forward arp request)
