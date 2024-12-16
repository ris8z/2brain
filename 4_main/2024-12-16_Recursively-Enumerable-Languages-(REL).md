---
date: 2024-12-16 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability & Complexity]]"
---

# Recursively Enumerable Languages (REL)
## Definitions
- A language $L \subseteq \Sigma^*$ is **recursively enumerable (REL)** or **semi-decidable** if:
  - There exists a *Turing Machine* (TM) *$M$* such that:
    - *halts* and *accepts* for every *$w \in L$*.
    - If *$w \notin L$*
      - *May never halt*, or
      - *Halt* and *reject*.
----------

- A language $L \subseteq \Sigma^*$ is **recursive (REC)** or **decidable** if:
  - There exists a *Turing Machine* (TM) *$M$* such that:
    - *halts* and *accepts* for every *$w \in L$*.
    - *halts* and *rejects* for every *$w \notin L$*.

## Non-REL Languages
- A language $L \subseteq \Sigma^*$ is **non-recursively enumerable (Non-REL)** 
  - if no *TM* can recognize $L$, even if it is allowed to run indefinitely.
- **Example**:
  - The complement of the *Halting Problem*:
    - $L = \{(M, w) \mid M \text{ does not halt on } w\}$.
    - There is no TM that can verify this property.
