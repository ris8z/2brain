---
date: 2024-12-18 
tags: 
    - CA341
hubs: 
    -   "[[2024-12-18_Comparative-Programming|Comparative Programming]]"
---

# Logic Programming

- **Overview**
  - *Purely Declarative*
  - Prolog descrive *cosa è vero, non come calcolarlo.*
- **Execution Order**
  - *Top-Down*: Prolog legge le clausole dall’alto verso il basso.
  - *Depth-First Search* : first valid solution or fail, then backtracking.

- **Unificazione e Risoluzione**
  - *Unificazione*: Prolog confronta e unifica due termini trovando i valori per le variabili.
    -  ```prolog
       ?- X = 3.            % X = 3
       ?- f(X, 2) = f(3, Y). % X = 3, Y = 2
       ```

  - *Risoluzione*: (Meccanismo logico che prova i goal usando)
    - Unificazione: Combina clausole.
    - Backtracking: Cerca soluzioni alternative in caso di fallimento.
    - ```prolog
        ancestor(X, Y) :- parent(X, Z), ancestor(Z, Y).
      ```

