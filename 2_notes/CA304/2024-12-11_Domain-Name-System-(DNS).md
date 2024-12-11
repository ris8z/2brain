---
date: 2024-12-11 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network]]"
---

# Domain Name System (DNS)

## What is it?
- A server with a *database* of ip addresses and thier domain names.
  - *distributed*
    - not only 1 database but splitted across the world
  - *strcutured*
    - Root Name Server, Top Level Domain Server, Authoritative Name Server
  - *replicated*
    - more copy of a single database

## DNS structure
![[Pasted image 20241211181952.png]]
- *Local Name Server (Last one)*
  - usually *located on the network* to which you pc is connected
  - when you make a request from home, you use your network *provider's name server*
  - *chace* the addresses of common domains

## How it works? (Address Resolution)
![[Pasted image 20241211183259.png]]

## DNS record
### Definition
- DNS records *store domain names*
  - if you have a website with a domain
    - you need to create DNS rcords for it
    - these are then sent to the relevant name servers

### DNS Records Summary

| **Type** | **Purpose**                                   | **Example**                                    |
|----------|-----------------------------------------------|------------------------------------------------|
| **A**    | Associates a domain with an IPv4 address      | `example.com IN A 207.26.21.46`                |
| **AAAA** | Associates a domain with an IPv6 address      | `example.com IN AAAA 2001:db8::ff00:42:8329`   |
| **CNAME**| Creates an alias for another domain           | `www IN CNAME example.com`                    |
| **MX**   | Specifies the mail servers for a domain       | `example.com IN MX 10 mailhost.example.com`    |
| **NS**   | Lists the name servers responsible for a domain | `example.com IN NS ns1.example.com`          |
| **PTR**  | Reverse DNS resolution (from IP to domain)    | `46 IN PTR example.com`                        |

## DNS optimisation
- You can see that this process takes time, and DNS servers
are queried frequently
- Solution:
  - local name servers *store the frequently visited* domain names in their cache
    - google.com
    - youtube.com
  - They *also* store domain names *based on geography*
    - rte.ie
    - met.ie

