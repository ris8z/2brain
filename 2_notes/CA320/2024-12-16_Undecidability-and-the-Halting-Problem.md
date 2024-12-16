---
date: 2024-12-16 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability & Complexity]]"
---

# Undecidability and the Halting Problem
## Theorem
The language *$A_{TM} = \{\langle M, w \rangle \mid M \text{ is a Turing machine and } M \text{ accepts } w \}$* is *undecidable*.

## Proof
Let’s assume a Turing machine $H$ is a decider for $ATM$.

$$
H(\langle M, w \rangle) =
\begin{cases} 
\text{accept}, & \text{if } M \text{ accepts } w \\
\text{reject}, & \text{if } M \text{ halts and does not accept } w
\end{cases}
$$

Let $D$ be a Turing machine that uses $H$ as follows:

1. Run $H$ on input $\langle M, M \rangle$.
2. Output the opposite of what $H$ produces.

Formally:

$$
D(M) =
\begin{cases} 
\text{accept}, & \text{if } M \text{ halts and does not accept } M \\
\text{reject}, & \text{if } M \text{ accepts } M
\end{cases}
$$

## Proof (continued)
If we run $D$ on its own description, we get:

$$
D(D) =
\begin{cases} 
\text{accept}, & \text{if } D \text{ halts and does not accept } D \\
\text{reject}, & \text{if } D \text{ accepts } D
\end{cases}
$$

This leads to a contradiction because $D(D)$ cannot both accept and reject itself. 

Thus, the initial assumption that $ATM$ is decidable is false.

## Theorem
The language $HALT_{TM} = \{\langle M, w \rangle \mid M \text{ is a Turing machine and } M \text{ halts on input } w\}$ is undecidable.

## Proof

- Assume that *$R$* is a TM that decides $HALT_{TM}$.
- Using *$R$*, we can construct a Turing machine *$S$* that decides *$A_{TM}$*.
- Since *$A_{TM}$ is undecidable*, the *initial assumption* that there exists a Turing machine that decides $HALT_{TM}$ must be *false*.


## Reducibility (How to use the halting problem)
### Definition

The language $L_1$ is **mapping reducible** to the language $L_2$, written as $L_1 \leq L_2$, if there exists a computable function $f : \Sigma^* \to \Sigma^*$ such that for every $w$:

$$
w \in L_1 \iff f(w) \in L_2
$$

### Implications

1. If $L_1 \leq L_2$ and $L_2$ is **decidable**, then $L_1$ is **decidable**.
2. If $L_1 \leq L_2$ and $L_2$ is **undecidable**, then $L_1$ is **undecidable**.
