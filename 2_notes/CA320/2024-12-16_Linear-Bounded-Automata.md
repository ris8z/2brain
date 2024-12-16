---
date: 2024-12-16 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability & Complexity]]"
---

# Linear Bounded Automata

- A **linear bounded automaton (LBA) Strucure** 
  - is a *finite state machine* 
  - with a finite length data store called a *tape*.
    - it consists of a sequence of cells, where each cell can store a symbol. 
    - used for store data and calculations
    - "[" and "]" marks the bound of the tape
  - with a *read-write head*, that can be moved left or righto one cell.

- **How it works?**
  - At each step the LBA read the symbol under the read-write head,
  - replaces it with another symbol 
  - then perform one of four possible actions *A ∈ {Y , N, L, R}*, where:
    - *Y* accept the input string
    - *N* reject the input string
    - *L* move the read-write head one cell to the left
    - *R* move the read-write head one cell to the right

- **Formally, a linear bounded automaton is a 5-tuple**
  - *$M = \{Q, \Sigma, \Gamma, q_0, \delta\}$*
    - *$Q$* is a finite set of states.
    - *$\Sigma$* is a finite alphabet (input symbols).
    - *$\Gamma$* is a finite alphabet (store symbols).
    - *$q_0 \in Q$* is the initial state.
    - *$\delta$* $: Q \times (\Gamma \cup \{[, ]\}) \to Q \times (\Gamma \cup \{[, ]\}) \times A$ is the transition function.
      - If *$((q, \sigma), (q', \psi, A)) \in \delta$*, then when in state $q$ with $\sigma$ at the current read-write head position, *$M$ will*:
        1. Replace *$\sigma$* by *$\psi$*,
        2. Perform action *$A$*, and
        3. Enter state *$q'$*.

- **Acceptance Condition**
  - The automaton $M$ accepts $w \in \Sigma^*$ if it starts with the configuration:
  - $(q_0, [w])$
  - and eventually takes the action $Y$.
