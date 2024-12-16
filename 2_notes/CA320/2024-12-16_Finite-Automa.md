---
date: 2024-12-16 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability & Complexity]]"
---

# Finite Automa

## DFA
- A **Deterministic Finite Automaton (DFA)** is a 5-tuple *$(Q, \Sigma, q_0, A, \delta)$* where:
  - *$Q$*: A finite set of states.
  - *$\Sigma$*: A finite input alphabet.
  - *$q_0 \in Q$*: The initial state.
  - *$A \subseteq Q$*: The set of accepting (or final) states.
  - *$\delta : Q \times \Sigma \to Q$*: The transition function.

- **Expanded Transiction Function** $\delta^*$
  1. *Base case* 
     $$
     \forall q \in Q, \ \delta^*(q, \epsilon) = q
     $$
  
  2. *Rec body*
     $$
     \forall q \in Q, \forall y \in \Sigma^*, \forall \sigma \in \Sigma, \ \delta^*(q, y\sigma) = \delta(\delta^*(q, y), \sigma)
     $$

## NFA
- **Nondeterministic Finite Automaton (NFA)**
  - It is a DFA where it's transition function can spit out more the one state,
  - and change state without consuming a symbol.
  - in fact the only change is the transition function:
    - *$\delta : Q \times (\Sigma \cup \{\Lambda\}) \to 2^Q$*
  - and the concept of *$\Lambda(S)$*
    - set of all states that u can reach without using a symbol
- **Expanded Transiction Function** $\delta^*$
  1. *Base case* 
  $$
  \forall q \in Q, \ \delta^*(q, \Lambda) = \Lambda(\{q\})
  $$
  2. *Rec body*
  $$
  \delta^*(q, y\sigma) = \Lambda\left( \bigcup_{p \in \delta^*(q, y)} \delta(p, \sigma) \right)
  $$
## Define Language using $\delta^*$
$$
L_M = \{ x \in \Sigma^* \mid \delta^*(q_0, x) \in A \}
$$

----------

## Summary
1. *Equivalence in Power*:
   - Every NFA can be converted into an equivalent DFA that recognizes the same language. This means NFAs and DFAs are equally powerful in terms of the languages they can recognize (the class of regular languages).

2. *Simplicity vs. Size*:
   - While DFAs have a single unique transition for each symbol from a state, NFAs allow multiple transitions (including \(\varepsilon\)-transitions). However, converting an NFA to a DFA may result in an exponential increase in the number of states.

3. *Determinism*:
   - A DFA has exactly one computation path for a given input string, whereas an NFA can have multiple paths (or none) and "guesses" the correct one through nondeterminism.

4. *Efficiency*:
   - DFAs are generally faster for implementation since they require only one transition per input symbol. NFAs, though conceptually simpler, may need backtracking or parallel exploration of multiple paths during simulation.

