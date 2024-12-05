---
date: 2024-12-05 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|Advanced Algorithms and AI Search]]"
---

# Cost function NeuralNetwork

## La funzione di costo $J$ 

$J$ è una funzione scalare che rappresenta l'errore totale del modello. Dipende dai pesi 

$$
\mathbf{w} = (w_1, w_2, \dots, w_n)
$$ 

e dai dati di input.


Esempio:

$$
J(\mathbf{w}) = \frac{1}{2} \sum (y - O)^2
$$

Qui $J$ misura la distanza tra l'output predetto $y$ e il target $O$.

---

## Il gradiente di $J$

Il gradiente di $J$, indicato con $\nabla J$, è il vettore delle derivate parziali di $J$ rispetto a ciascun peso $w_i$:

$$
\nabla J(\mathbf{w}) = \begin{bmatrix}
\frac{\partial J}{\partial w_1} \\
\frac{\partial J}{\partial w_2} \\
\vdots \\
\frac{\partial J}{\partial w_n}
\end{bmatrix}
$$

Ogni componente del gradiente misura quanto e in che direzione modificare ciascun peso $w_i$ per aumentare $J$.


- Esempio

$$
J(w_1, w_2) = w_1^2 + w_2^2
$$

$$
\frac{\partial J}{\partial w_1} = 2w_1, \quad \frac{\partial J}{\partial w_2} = 2w_2
$$

$$
\nabla J(w_1, w_2) = \begin{bmatrix}
2w_1 \\
2w_2
\end{bmatrix}
$$

---

## Ruolo del gradiente nella discesa del gradiente

Il gradiente $\nabla J$ indica la direzione di massimo incremento della funzione $J$.
Nella discesa del gradiente, invece, vogliamo **ridurre** $J$, quindi aggiorniamo i pesi nella direzione opposta al gradiente:

$$
w_i := w_i - \eta \cdot \frac{\partial J}{\partial w_i}
$$

Il **gradiente** ci dice in quale direzione andare (positivo o negativo).
La **sua intensità** ci dice quanto spostarci (maggiore il valore, più significativo il cambiamento).

