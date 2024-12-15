---
date: 2024-12-15 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability and Complexity]]"
---

# Regular Languages

## Regular Languages
The set of **regular languages** $R$ over an alphabet $\Sigma$ is defined as:

1. The language $\emptyset$ is an element of $R$:
   $$
   \emptyset \in R
   $$

2. For every $a \in \Sigma$, the language $\{a\}$ is in $R$:
   $$
   \forall a \in \Sigma, \{a\} \in R
   $$

3. For all $L_1, L_2 \in R$, the following languages are also in $R$:
   - **Union**:
     $$
     L_1 \cup L_2 \in R
     $$
   - **Concatenation**:
     $$
     L_1 L_2 \in R
     $$
   - **Kleene Star**:
     $$
     L_1^* \in R
     $$

---

## Regular Expression

### Definition:
Every **regular language** can be represented by a **regular expression**, and every **regular expression** represents a **regular language**.

- $\emptyset$ and $\epsilon$ are regular expressions.
- $\forall a \in \Sigma$, $a$ is a regular expression.
- If $R_1$ and $R_2$ are regular expressions, the following are also regular expressions (in order of precedence):
  1. **Parentheses**: $(R_1)$
  2. **Closure**: $R_1^*$
  3. **Concatenation**: $R_1 R_2$
  4. **Alternation (Union)**: $R_1 + R_2$

---

### Examples:

| **Regular Language**                                | **Regular Expression**                                      |
|-----------------------------------------------------|------------------------------------------------------------|
| $$\emptyset$$                                       | $$\emptyset$$                                              |
| $$\{a\}$$                                           | $$a$$                                                     |
| $$\{a, b\}^*$$                                      | $$(a + b)^*$$                                              |
| $$\{aab\}^*$$                                       | $$aab^*$$                                                  |
| $$\{aa, bb, ab, ba\}^*$$                            | $$(aa + bb + ab + ba)^*$$                                  |
| $$\{aa, bb\} \cup \{ab, ba\}\{aa, bb\}^*\{ab, ba\}$$| $$(aa + bb + (ab + ba)(aa + bb)^*(ab + ba))^*$$            |

---

### Properties of Regular Expressions:

1. **Closure of Kleene**:
   $$
   R^* = R^*R^* = (R^*)^* = R + R^*
   $$

2. **Concatenation Cycle**:
   $$
   R_1(R_2R_1)^* = (R_1R_2)^*R_1
   $$

3. **Distribution with Kleene Star and Union**:
   $$
   (R_1^*R_2)^* = \epsilon + (R_1 + R_2)^*R_2
   $$

4. **Cycle with Concatenation and Kleene**:
   $$
   (R_1R_2^*)^* = \epsilon + R_1(R_1 + R_2)^*
   $$

---

## Deterministic Finite Automa

### Definition
A **Deterministic Finite Automaton (DFA)** is a 5-tuple $(Q, \Sigma, q_0, A, \delta)$ where:

- **$Q$**: A finite set of states.
- **$\Sigma$**: A finite input alphabet.
- **$q_0 \in Q$**: The initial state.
- **$A \subseteq Q$**: The set of accepting (or final) states.
- **$\delta : Q \times \Sigma \to Q$**: The transition function.

---

### Key Concepts

#### Transition Function ($\delta$)
- For any **state $q \in Q$** and any **input symbol $\sigma \in \Sigma$**, the transition function $\delta(q, \sigma)$ determines:
  - The **next state** the DFA moves to when it receives input $\sigma$ while in state $q$.

#### Characteristics of a DFA
- **Deterministic behavior**: At any given state, for a specific input symbol, the next state is uniquely determined by $\delta$.
- The automaton processes **one symbol at a time** from the input string.

#### Acceptance
- A DFA **accepts** an input string if, after processing the string, it ends in one of the accepting states $A$.

---

### Summary
A DFA is a mathematical model for recognizing patterns within strings of symbols. Its **deterministic** nature ensures that for every state and input, the behavior is uniquely defined.

### Examples
#### Strings ending in b without substring aa
![[Pasted image 20241215035655.png]]
- *Regular Expression* 
  - $(b + ab)*b$

#### Strings dividble by 3 and not start with 01 
![[Pasted image 20241215044637.png]]
- *What sort of binary strings will it not accept?*
  - starting with 01
  - with n % 3 != 0

### Extended Transition function
La funzione $\delta^*$ è un'estensione ricorsiva della funzione di transizione $\delta$ per stringhe arbitrarie $x \in \Sigma^*$, dove $\Sigma^*$ rappresenta l'insieme di tutte le stringhe (inclusa la stringa vuota $\epsilon$).

---

#### Definizione Formale di $\delta^*$
1. **Caso base** (stringa vuota $\epsilon$):
   $$
   \forall q \in Q, \ \delta^*(q, \epsilon) = q
   $$
   - Leggere la stringa vuota da uno stato $q$ **non cambia** lo stato corrente.

2. **Caso ricorsivo** (stringa non vuota $y\sigma$, con $y \in \Sigma^*$ e $\sigma \in \Sigma$):
   $$
   \forall q \in Q, \forall y \in \Sigma^*, \forall \sigma \in \Sigma, \ \delta^*(q, y\sigma) = \delta(\delta^*(q, y), \sigma)
   $$
   - Si calcola prima lo stato raggiunto leggendo la stringa $y$ partendo da $q$ (usando $\delta^*$).
   - Poi si applica la funzione di transizione $\delta$ al risultato ottenuto e al simbolo successivo $\sigma$.

---

#### Accettazione di una Stringa $x$
Una stringa $x \in \Sigma^*$ viene accettata da un DFA $M$ se:
$$
\delta^*(q_0, x) \in A
$$
- $q_0$: Stato iniziale.  
- $\delta^*(q_0, x)$: Stato finale raggiunto dopo aver letto tutta la stringa $x$.  
- $A$: Insieme degli stati di accettazione.  

Se $\delta^*(q_0, x)$ **non appartiene** ad $A$, la stringa viene **rifiutata**.

---

#### Linguaggio Accettato da un DFA
Il **linguaggio accettato** da un DFA $M$ è definito come:
$$
L(M) = \{ x \in \Sigma^* \mid \delta^*(q_0, x) \in A \}
$$
- $L(M)$: Insieme di tutte le stringhe accettate dal DFA $M$.

