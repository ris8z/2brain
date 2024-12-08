---
date: 2024-12-08 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network]]"
---

# Network Address Translation (NAT)

## What it does?
translate *private* address into *public* ones.
to let an *host* access the *internet*.

## Who it does it?
the *router*

## How it does it?
![[Pasted image 20241208162320.png]]
- All the outgoint packets go through the *NAT router*
  - It raplace the *source ip* with the public ip

- All incoming packest go through the *Nat router*
  - it replace the *destination ip* with the private ip
  - using a translation table

## How does look the translation table?


### Esempio

Supponiamo che due dispositivi interni vogliano accedere a un sito web esterno (IP: `8.8.8.8`, porta `80`):

| **Private Address**  | **Private Port** | **NAT Public Address**  | **NAT Public Port** | **External Address**  | **External Port** | **Protocol** |
|----------------------|------------------|-------------------------|---------------------|-----------------------|-------------------|--------------|
| 192.168.1.2          | 12345            | 203.0.113.1             | 50000               | 8.8.8.8               | 80                | TCP          |
| 192.168.1.3          | 12346            | 203.0.113.1             | 50001               | 8.8.8.8               | 80                | TCP          |

### Dettagli

- **NAT Public Port**:
  - Dispositivo `192.168.1.2 : 12345` -> NAT -> `203.0.113.1 : 50000`.
  - Dispositivo `192.168.1.3 : 12346` -> NAT -> `203.0.113.1 : 50001`.

- **External Port**:
  - Entrambi i dispositivi accedono al servizio web sulla porta `80` del server `8.8.8.8`.
