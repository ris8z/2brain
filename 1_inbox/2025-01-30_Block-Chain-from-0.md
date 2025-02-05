---
date: 2025-01-30 
tags: 
    - blockchain
---

# Block Chain from 0

## Sha256 hash alogithm

### Code
```python
import hashlib
h = hashlib.sha256()
h.update('a'.encode('utf-8'))
h.hexdigest() # -> 'ca978112ca1bbdcafac231b39a23dc4da786eff8147c4e72b9807785afee48bb'
```
### How
For each data encoded in byte it spit out a *256 bit number* rappresenting the *hash of that data*.
So all possible different hashs are *2 ^ 256* = 115792089237316195423570985008687907853269984665640564039457584007913129639936
For semplicity we rappresent that in hexdeciaml so it is shorter to rappresnt.

### Key point
- same data -> same result (i.e. my hash of 'a' is going be equals to all other hashes of 'a')
- minor change in the data -> different result (i.e. hash of 'ab' is going to be different from hash of 'ac')
- data -> hash (easy and fast)
- hash -> data (almost impossible and slow)
