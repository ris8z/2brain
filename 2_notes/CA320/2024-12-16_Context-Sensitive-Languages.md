---
date: 2024-12-16 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability & Complexity]]"
---

# Context Sensitive Languages

## Definition

- An **unrestricted grammar** is a 4-tuple 
  - G = (V , Σ, S, P)
  - where *V* and *Σ* are *disjoint* sets of variables and terminals respectively.
  - *S* ∈ V is called the *start symbol*
  - *P* is a set of *production rules* of the form *α → β*

- A **Context-Sensitive Grammar (CSG)** 
  - is an *unrestricted grammar*
  - in which *every production* is of the form *α → β and |β| ≥ |α|*
  - i.e. no production rule is reduce the len of the str.

- **Example of Context-Sensitive-Language**
  - Iconic
    - $$
      L = \{ a^n b^n c^n \mid n \geq 0 \}
      $$

