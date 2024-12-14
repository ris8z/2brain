---
date: 2024-12-14 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability & Complexity]]"
---

# Introduction

## Logic
### Basic Opreations
| Connective     | Symbol   | Use      | English equivalent     |
|----------------|----------|----------|------------------------|
| Conjunction    | ∧        | p ∧ q    | p and q                |
| Disjunction    | ∨        | p ∨ q    | p or q                 |
| Negation       | ¬        | ¬p       | not p                  |
| Conditional    | →        | p → q    | if p then q, p only if q |
| Biconditional  | ↔        | p ↔ q    | p if and only if q     |

### Truth tables
| p   | q   | p ∧ q | p ∨ q | p → q | p ↔ q |
|-----|-----|-------|-------|-------|-------|
| T   | T   | T     | T     | T     | T     |
| T   | F   | F     | T     | F     | F     |
| F   | T   | F     | T     | T     | F     |
| F   | F   | F     | F     | T     | T     |

### Rules
| Law                 | Expression             | Equivalent Expression                |
|---------------------|------------------------|--------------------------------------|
| Commutative         | p ∨ q                  | q ∨ p                                |
|                     | p ∧ q                  | q ∧ p                                |
| Associative         | p ∨ (q ∨ r)            | (p ∨ q) ∨ r                          |
|                     | p ∧ (q ∧ r)            | (p ∧ q) ∧ r                          |
| Distributive        | p ∨ (q ∧ r)            | (p ∨ q) ∧ (p ∨ r)                    |
|                     | p ∧ (q ∨ r)            | (p ∧ q) ∨ (p ∧ r)                    |
| De Morgan’s         | ¬(p ∧ q)               | ¬p ∨ ¬q                              |
|                     | ¬(p ∨ q)               | ¬p ∧ ¬q                              |
| Implication         | p → q                  | ¬p ∨ q                               |
| Biconditional       | p ↔ q                  | (p → q) ∧ (q → p)                    |
| Contrapositive      | p → q                  | ¬q → ¬p                              |


### Definition 
- *compound proposition* is a proposition made of an arbitrary combination of the 5 basic operations (∧,∨,¬,→ ↔).
- *tautology* is a compound proposition that is always true.
- *contradiction* is a compound proposition that is always false.


### Logic Equivalance & Implication
- *$P \iff Q$* != (P ↔ Q)
  - P and Q are logically equivalent if *P* and *Q* have the *same truth table*.
- *$P \implies Q$* != (P → Q)
  - P logically implies Q if in every case *P is True then Q is also True*.

### Quantifiers
- $\forall x \, (P(x)) \iff \neg (\exists x \, (\neg P(x)))$
- $\exists x \, (P(x)) \iff \neg (\forall x \, (\neg P(x)))$

## Set
- *Union, Intersection, and Difference*:
  - $A \cup B = \{x \mid x \in A \lor x \in B\}$ (Union)
  - $A \cap B = \{x \mid x \in A \land x \in B\}$ (Intersection)
  - $A - B = \{x \mid x \in A \land x \notin B\}$ (Difference)

- *Disjoint Sets*:
  - $A \cap B = \emptyset$:  $A$ and $B$ are disjoint.
  - A collection of sets is *pairwise disjoint* if distinct pairs $A$ and $B$ from the collection are disjoint.

- *Complement of a Set*:
  - $A' = \{x \mid x \in U \land x \notin A\}$, where $U$ is the universal set.

- *De Morgan’s Laws*:
  - $(A \cup B)' = A' \cap B'$
  - $(A \cap B)' = A' \cup B'$

- *Cartesian Product*:
  - $A \times B = \{(a, b) \mid a \in A \land b \in B\}$
  - The elements of $A \times B$ are *ordered pairs*, where $(a, b) = (c, d)$ only if $a = c$ and $b = d$.

## Relations and Functions
### Relations
- *$R$* is a relation on two sets $A$ and $B$ is a set of order pairs $A \times B$
- where:
  - $A$ is the domain
  - $B$ is the codomain
- if:
  - $x \in A$
  - $y \in B$
- then:
  - $x R y \text{ is true if } (x, y) \in R$
### Functions
- *$f : A \to B$* is a special kind of relations where:
  - an elment of the domain can be linked just to one element of the codomain
- can be:
  - *one-two-one* if it never assign the same value to 2 different element of its domain.
  - *onto* if domain and codomain are the same
  - *bijection* if a function is both one-two-one and onto

### Equivalence Relations
A **relation** $R$ on a set $A$ is an **equivalence relation** if it satisfies the following three conditions:

1. **Reflexive** (Every element is related to itself.):  
   $$ \forall x \in A, \, xRx $$  
   

2. **Symmetric** (If $x$ is related to $y$, then $y$ is related to $x$.):  
   $$ \forall x, y \in A, \, xRy \implies yRx $$  
   

3. **Transitive** (If $x$ is related to $y$, and $y$ is related to $z$, then $x$ is related to $z$.):  
   $$ \forall x, y, z \in A, \, (xRy \land yRz) \implies xRz $$  
   
### Equivalent Classes

For an equivalence relation $R$ on a set $A$, and an element $x \in A$, the **equivalence class** containing $x$ is:

$$
[x] = \{y \in A \mid (x,y) \in R\}
$$

Or more formal:
$$
[x] = \{y \in A \mid yRx\}
$$

- This is the set of all elements $y$ in $A$ that are related to $x$ under $R$.
- example
  - ![[Pasted image 20241214231010.png]]
  - you can just use [1] to rappresent the class for 3 and 5 also
  - and 2 for rappresent the class also for 4

## Proofs
### Contrapostive
#### Key Equivalence
We know:
- $p \to q \equiv \neg q \to \neg p$

---

#### Example Problem
Prove:  
$$
\forall i, j, n, \text{ if } ij = n \text{ then } i \leq \sqrt{n} \text{ or } j \leq \sqrt{n}.
$$

#### Strategy
Instead of proving:
$$
ij = n \to (i \leq \sqrt{n} \lor j \leq \sqrt{n}),
$$
we prove its **contrapositive**:
$$
\neg (i \leq \sqrt{n} \lor j \leq \sqrt{n}) \to ij \neq n.
$$

---

#### Step-by-Step Proof

1. **Negate the conclusion of the implication**:
   $$ 
   \neg (i \leq \sqrt{n} \lor j \leq \sqrt{n})
   $$

2. **Apply De Morgan's Law**:
   $$ 
   \neg (i \leq \sqrt{n} \lor j \leq \sqrt{n}) \equiv \neg (i \leq \sqrt{n}) \land \neg (j \leq \sqrt{n})
   $$

3. **Rewrite the negations**:
   $$ 
   \neg (i \leq \sqrt{n}) \equiv i > \sqrt{n}, \quad \neg (j \leq \sqrt{n}) \equiv j > \sqrt{n}.
   $$
   So:
   $$ 
   \neg (i \leq \sqrt{n} \lor j \leq \sqrt{n}) \equiv (i > \sqrt{n}) \land (j > \sqrt{n}).
   $$

4. **Combine the conditions**:
   If $i > \sqrt{n}$ and $j > \sqrt{n}$, then:
   $$ 
   ij > \sqrt{n} \cdot \sqrt{n}.
   $$

5. **Simplify**:
   $$ 
   ij > n \implies ij \neq n.
   $$

---

#### Conclusion
We have proven the contrapositive:
$$
\neg (i \leq \sqrt{n} \lor j \leq \sqrt{n}) \to ij \neq n,
$$
which implies the original statement is true by the equivalence of a statement and its contrapositive.

---
#### Key Notes
- **De Morgan's Law**: Used to transform $\neg (a \lor b)$ into $\neg a \land \neg b$.
- **Contrapositive Proof**: Often simplifies the logic by flipping the direction of reasoning.


### Contradiction
#### Key Idea:
- Every proposition $p$ is equivalent to the proposition 
  $$
  true \to p
  $$
- Its contrapositive is: 
  $$
  \neg p \to false.
  $$
- **Proof by contradiction** works by assuming $p$ is false (i.e., $\neg p$) and deriving a contradiction (i.e., deriving $false$).

---
#### Example Problem
Prove:
$$
\forall m, n \in \mathbb{N}, \frac{m}{n} \neq \sqrt{2}
$$

---
#### Step-by-step-Proof
1. **Assume the negation of the proposition**:
   - Assume $\exists m, n \in \mathbb{N}$ such that:
     $$
     \frac{m}{n} = \sqrt{2}.
     $$

2. **Simplify to irreducible form**:
   - By removing common factors, write:
     $$
     \frac{p}{q} = \sqrt{2},
     $$
     where $p$ and $q$ are integers with no common factors.

3. **Square both sides**:
   - Multiply through to eliminate the square root:
     $$
     p^2 = 2q^2.
     $$
   - This implies $p^2$ is **even**.

4. **Show that $p$ must also be even**:
   - If $p^2$ is even, then $p$ must be even (since only even numbers squared produce even results).
   - Let $p = 2r$, where $r \in \mathbb{N}$.

5. **Substitute $p = 2r$ into $p^2 = 2q^2$**:
   - Expand:
     $$
     (2r)^2 = 2q^2 \implies 4r^2 = 2q^2 \implies 2r^2 = q^2.
     $$

6. **Show that $q$ must also be even**:
   - Since $q^2 = 2r^2$, $q^2$ is also even, meaning $q$ must be even.

7. **Contradiction**:
   - If both $p$ and $q$ are even, they have a common factor of $2$, contradicting the assumption that $p$ and $q$ have no common factors.

8. **Conclusion**:
   - The assumption $\frac{m}{n} = \sqrt{2}$ leads to a contradiction. Therefore:
     $$
     \forall m, n \in \mathbb{N}, \frac{m}{n} \neq \sqrt{2}.
     $$

---
### By Cases
### By Structural Induction

## Languages
- *Why?*
  - We use languages to describe a problem without solving it
  - We handle **decision problem** (only possible solution Yes/No)

- *How?*
  - For any given **decision problem** $\Pi$, we can partition the set of inputs into two sets:
    1. **$Y_\Pi$**: Input values that result in the answer "yes."
    2. **$N_\Pi$**: Input values that result in the answer "no."
  
  - Let’s focus on the set of input values that result in the answer "yes," denoted as $Y_\Pi$:
    - Each element of $Y_\Pi$ can be thought of as a **word** in a language $L_\Pi$.
    - The complete set $Y_\Pi$ corresponds to the **complete language** $L_\Pi$.
  
  - A machine that determines whether a word belongs to the language $L_\Pi$:
    - **Accepts** the language $L_\Pi$.
    - **Solves** the related decision problem $\Pi$.
