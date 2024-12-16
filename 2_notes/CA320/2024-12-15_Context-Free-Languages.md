---
date: 2024-12-15 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability and Complexity]]"
---

# Context Free Languages

- A **context-free grammar (CFG)** is a 4-tuple G = (N, Σ, S, P) where
  - *N* is a set of nonterminal symbols, or *variables*,
  - *Σ* is a set of terminal symbols, and N and Σ are disjoint finite sets,
  - *S* is a special nonterminal (S ∈ N) called the *start symbol*,
  - *P* is a finite *set of grammar rules*, or productions, 
    - of the form 
      - *A → α*, 
      - where A ∈ V and *α ∈ (N ∪ Σ)*.
  - The set *V = N ∪ Σ* is called the *vocabulary* of G .



> [!TIP]
> *CFG* is a *unrestricted grammar* with result of the production rules made only of
variable or terminals or both

- **Pumping Lemma**: If *L* is a *context-free language* there is an integer *n* (called Pumping length)
- such that
  - any string in L with len > n, *∀u ∈ L* with *|u| ≥ n*
  - must be splitted in vwxys,  *u = vwxyz* 
  - must respect this tree condition
    1. *|wy| > 0*
    2. *|wxy| ≤ n*
    3. *$\forall m \geq 0, \; vw^m xy^m z \in L$*

- **Examples of Context-Free-Languages**
  - Iconic one
    - $$
      L_1 = \{ 0^n 1^n \mid n \geq 0 \}
      $$
  - Simple Pal
    - $$
      L_2 = \{ w c w^R \mid w \in \{0, 1\}^*   \}
      $$
  - Evan Pal
    - $$
      L_3 = \{ ww \mid w \in \{0, 1\}^* \}
      $$

