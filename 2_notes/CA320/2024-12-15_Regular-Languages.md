---
date: 2024-12-15 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability and Complexity]]"
---

# Regular Languages

- The set of **regular languages** *$R$* over an alphabet *$\Sigma$* is defined as:
  1. *$\emptyset \in R$*
  
  2. *$\forall a \in \Sigma, \{a\} \in R$*
  
  3. *$\forall (L_1, L_2) \in R$* 
     - $L_1 \cup L_2 \in R$
     - $L_1 L_2 \in R$
     - $L_1^* \in R$

- Every **regualr expression** rappresent a regual languages
  - *$\emptyset$* and *$\epsilon$* are regular expressions.
  - *$\forall a \in \Sigma$*, *$a$* is a regular expression.
  - If *$R_1$* and *$R_2$* are regular expressions, also these are RE
    1. $(R_1)$
    2. $R_1^*$
    3. $R_1 R_2$
    4. $R_1 + R_2$
- **RL vs RE**
  - | *Regular Language*                                  | *Regular Expression*                                       |
    |-----------------------------------------------------|------------------------------------------------------------|
    | $$\emptyset$$                                       | $$\emptyset$$                                              |
    | $$\{a\}$$                                           | $$a$$                                                      |
    | $$\{a, b\}^*$$                                      | $$(a + b)^*$$                                              |
    | $$\{aab\}^*$$                                       | $$aab^*$$                                                  |
    | $$\{aa, bb, ab, ba\}^*$$                            | $$(aa + bb + ab + ba)^*$$                                  |
    | $$\{aa, bb\} \cup \{ab, ba\}\{aa, bb\}^*\{ab, ba\}$$| $$(aa + bb + (ab + ba)(aa + bb)^*(ab + ba))^*$$            |


- **Pumping Lemma**: If *L* is a *context-free language* there is an integer *p* (called Pumping length)
  - such that
    - any string in L with len > n, *∀s ∈ L* with *|s| ≥ n*
    - must be splitted in xys,  *s = xyz* 
    - must respect this tree condition
      1. *|y| > 0*
      2. *|xy| ≤ p*
      3. *$\forall i \geq 0, \; xy^iz \in L$*
  
- **Examples of Regular-Languages**
  - Number in bin divisible by 3 over {0,1}*
  - Strings that end in 11 over {0,1}*
  - Strings that end in b without sub string aa {a,b}*

