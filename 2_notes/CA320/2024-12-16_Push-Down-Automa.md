---
date: 2024-12-16 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability & Complexity]]"
---

# Push Down Automa

- A **Pushdown Automaton (PDA)** is a 7-tuple
  - M = (Q, Σ, Γ, q0, Z0, A, δ) where
    - *Q* is a finite set of states
    - *Σ* and *Γ* are finite input and stack alphabets;
    - *q0 ∈ Q* is the start state;
    - *Z0 ∈ Γ* is the start stack symbol;
    - *A ⊆ Q* is the set of accepting states;
    - *$\delta$* $: Q \times (\Sigma \cup \{\epsilon\}) \times \Gamma \to 2^{(Q \times \Gamma^*)}$

- **Iconic**
  - ![[Pasted image 20241216043827.png]]
- **Simple Pal** (deterministic)
  - ![[Pasted image 20241216043922.png]]
- **Even pal** (non-deterministi)
  - ![[Pasted image 20241216043902.png]]
