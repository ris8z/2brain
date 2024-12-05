---
date: 2024-12-05 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|Advanced Algorithms and AI Search]]"
---

# GA vs NN vs SSS

## Comparison of Neural Networks and Genetic Algorithms (GAs)

### Similarities
- **Search Process:**
  - Both climb/descend an unknown multi-dimensional landscape.
  - The actual shape of the landscape is never revealed; it is deduced from finite sample points.
  - Neither guarantees finding the global maximum/minimum due to the possibility of requiring infinite exploration.
- **Avoiding Local Optima:**
  - Both introduce "noise" to escape local optima.
  - High probability of noise at the start, declining as the search progresses.

---

### Differences

#### **For Neural Networks (NNs):**
- **Exemplars:**
  - Provided with well-chosen, representative inputs and outputs.
- **Error Knowledge:**
  - $E$ (distance from the correct answer) is known.
  - $\frac{\partial E}{\partial w}$ (how error changes with parameters) is also known.
- **Directed Moves:**
  - Can make directed moves based on gradients.
  - Begins by climbing/descending multiple landscapes and eventually specializes in a specific family of landscapes.

#### **For Genetic Algorithms (GAs):**
- **Exemplars:**
  - Generates its own exemplars.
- **Fitness Knowledge:**
  - $E$ (the "correct" answer) is not known; only a fitness score for the attempt is given.
  - $\frac{\partial f}{\partial w}$ (how fitness changes with parameters) is not known.
- **Random Moves:**
  - Can only make random moves.
- **Population Approach:**
  - Uses multiple climbers/descenders on the same landscape.
  - Follows the best performers while maintaining diversity by exploring multiple trails simultaneously.

---

### Functional Goals

#### **Neural Networks:**
- Goal: Match $n$-dimensional Input with the correct Output.
- Represent the function over its entire range.
- **Requirements:**
  - Correct Outputs for many representative Inputs (spanning the range of the function).

#### **Genetic Algorithms:**
- Goal: Find the $n$-dimensional Input that produces the highest Output.
- Focus on maximizing the function, not representing it.
- **Requirements:**
  - For any given Input, provide the Output.

#### **Esempio**

- Supponiamo di avere una funzione matematica $f(x, y) = -x^2 + y^2$.
  - Con un NN:
    - Vorresti costruire una rete che possa prevedere il valore di $f(x, y)$ per qualsiasi combinazione di $x$ e $y$.
    - Il tuo obiettivo è mappare tutta la funzione.

  - Con un GA:
    - Stai cercando di trovare la coppia $(x, y)$ che porta al valore massimo di $f(x, y)$.
    - Non importa conoscere il comportamento completo della funzione, basta identificare che, ad esempio, $(x = 0, y = 100)$ massimizza $f(x, y)$ a $10,000$.

> [!TIP]
> WHAT ABOUT SSS? With State-Space Search, we often have a heuristic "distance from goal".
With GA, we have no idea how far away we might be from the optimal solution.
