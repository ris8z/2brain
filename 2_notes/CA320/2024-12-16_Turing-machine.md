---
date: 2024-12-16 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability & Complexity]]"
---

# Turing machine

## Description


- A **Turing machine** is similar to a *linear bounded automaton* (LBA)
  - except that the tape *is “semi-infinite”*.
  - *Tape* is made of squence of cells, each cell can hold a symgbol or be blank (blank symbol)
    - the tape start with "[" (left-most symbol)
    - the tape extend infinitly to the right
  - *Read-write head* can move one cell to left or right
- **How it works?**
  - At each step 
    - TM *reads* the symbol under the RW-head, *replaces* it with another symbol
    - and then *performs* one of three possible actions
    - *A ∈ {L, R, S}*, where:
      - *L* denotes “Left”
      - *R* denotes “Right”
      - *S* denotes “Stationary”
- **New issue**
  - Because the tape is “semi-infinite” 
  - The Turing machine *may not halt at all*.

## Formal

A **Turing machine (TM)** is defined as a 5-tuple $T = (Q, \Sigma, \Gamma, q_0, \delta)$ where:

- *$Q$*: A finite set of states.
  - Includes two special states, $h_a$ (accepting state) and $h_r$ (rejecting state), which are not elements of $Q$.

- *$\Sigma$*: The finite input alphabet.

- *$\Gamma$*: The finite tape alphabet.
  - $\Gamma \supseteq \Sigma$.
  - Includes the blank symbol $\Delta$, which is not an element of $\Gamma$.

- *$q_0 \in Q$*: The initial state.

- *$\delta$*: The transition function.
  - $\delta : Q \times (\Gamma \cup \{[,\Delta\}) \to (Q \cup \{h_a, h_r\}) \times (\Gamma \cup \{[,\Delta\}) \times \{R, L, S\}$.
    - $R$: Move the tape head to the right.
    - $L$: Move the tape head to the left.
    - $S$: Keep the tape head stationary.

## Universal

- **Overview**
  - A **Universal Turing Machine (UTM)** is a Turing machine capable of simulating any other Turing machine.
  - Instead of creating a specific Turing machine for each algorithm, the *UTM can execute any algorithm given*:

- **Input Format**
  - The UTM receives input in the form:
    $$
    e(T)e(z)
    $$
    where:
    - *$e(T)$*: Encoding of the Turing machine $T$. (implementing the algorithm)
    - *$e(z)$*: Encoding of the input $z$ for $T$.

- **How?**
  1. The UTM *reads $e(T)e(z)$* from the tape.
  2. *Decodes $e(T)$* to *simulate* the behavior of *$T$*.
  3. *Feeds $z$ into $T$* and performs the computation step by step.
  4. Produces *$e(y)$ if $T$ halts on $z$*.
----------

- **Significance**
  - *Universality*: A single machine can simulate any Turing machine, just like a general-purpose computer can execute any program.
  - *Foundation of Modern Computing*: Demonstrates the concept of programmable machines.
  - *Church-Turing Thesis*: Any algorithmic process can be represented by a Turing machine, and thus by a Universal Turing Machine.
