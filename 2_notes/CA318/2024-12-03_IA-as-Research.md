---
date: 2024-12-03 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|advanced]]"
---

# IA as Research

## Definition

- AI can be seen as a program that try to *generate new solution*, that the human programmers can not think. 
- Programmers duty is to:
  - define a *space of solution* of a problem.
  - define a *search algorithm* to find a good solution into the space defiened

## Search Algorithm

- *Exhaustive*
  - if the space is small enough, you can check all the possibile solution and pick the best one
- *Euristic*
  - if the space is too big, we use an euristic approach, a praticale rule that search a suitable solution
  in a limited amount of time, we no guarantee that it is the best one

## Local vs Global Optima/Maximum
- Local
  - a solution that is better than the ones near to it
- Global
  - the best solution inside the space

Algorithms do not Exhaustive risk to find just local optima.

## Heuristic (How does it work?)
- Define an *heuristic rule* to search the space.
  - give a good answer most of the time
  - no guarantee it won't fail
- Define an *Evaluation function* to judge how good a solution is.
  - this may be well-defiened (each solution has a strict score)
  - or the evaluation function itself may be heuristic (i.e. bestmove in chess)
  

## I.E. Heuristic search algorithm

```python
current = get_20_random_solution()
while True:
    best_10 = get_best_ten_solution_from(current, evaluation_function) 
    current = get_20_from_solution(best_10) 
#This apporach risk to get stuck into a local maximum or optima
```

## Heuristic different search approaches
1. *Random Search*:  
   - Random exploration of the solution space, useful for small spaces.  
2. *Metaheuristics*:  
   - Smart but domain-independent strategies. (i.e. chatGPT give not valid move for a chess board) 
3. *Specific Heuristics*:
   - Guided search using domain knowledge, more effective but requires more effort. (i.e. stockfish give always a valid move)


> [!TIP]
> How to find the max of a f(x): 
if the f(x) has an equation (dx = 0)
else plot f(x) with a lot of experiments (works only if the f(x) is contius and not caotic)


