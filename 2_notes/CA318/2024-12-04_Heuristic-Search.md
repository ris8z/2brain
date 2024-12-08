---
date: 2024-12-04 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|Advanced Algorithms and AI Search]]"
---

# Heuristic Search

## Uninformed search 
- / brute force serach (check all the possible inputs)

## informed search  
- / Heuristic search (use a problem-specific info to guide the search)
    - to do the next move, do not go down more level -> Hill climbing.
    - use an evaluating f(x) to estimate which child search first.

## Hill climbing
  - suppose we have a continus f(x).
  - you start from a point x and try to max the output f(x).
  - we tilt x by 0.1 or -0.1 and see which is the direction that lead f(x) to grow.
  - not going to go in a temporary wrose state to get the global maximum.
  - it may stop and porbably it will stop on the local maximum.

## Best first search
- *f(x)* evaluation function 
- *h(x)* heuristic guessed distance between state x and the goal
$$
f(x) = h(x)
$$
- it works as follow.
![alt text](https://humphryscomputing.com/Notes/Morelli.images/6.gif) 
- it choose the state with the best evaulation (by jumping the one with the worst).
- in poor words sorts the queue and as a key it as the evaluation function.
- Inaccuarte heuristic
  - the eval f(x) is only a guess. It is bound to be inaccuarte on some state.

## Alogrithm A (Best first search + Distance from start)
- *f(x)* evaluation function 
- *g(x)* distance between the state x and the start
- *h(x)* heuristic guessed distance between state x and the goal
$$
f(x) = g(x) + h(x)
$$
- a smaller value of *f(x)* means a more promesing state.
- *g(x)* grows as we explore deeply while *h(x)* esitmates how close we are to the goal

- By adding g(x) we prevent the algorithm to be overinfluenced by an innacurate h(x) (that we know it is invitable)
- How does it work?
  - when we follow a wrong *h(x)* estimation:
    - the increasing *g(x)* will eventually dominate the *h(x)*
    - frocing the alogrithm to backtrack and search new paths
- Eample?
  - 8 puzzle

## Admissibility
- An alogo is admissible if it guarantee to find the shortest path
  - BFS is admissible (but impratical)
  - A (with f(x) = g(x) + h(x)) is admissible is h(x) is well desined

## A* algorithms
- it is a specfic vestion of the A algorithm with and important condition
$$
h(x) <= hStar(x)
$$
- *h(x)* is heuristic estimate. 
- *hStar(x)* is the true distance from x to the goal
- This means:
  - the *h(x)* is *optimistic* (it never overestimate the acuatl distance between x and the goal)
  - I.E. *h(x) = 0*, (in this case A* is basically a BFS)
- Why this works:
  - When A* finishes, it has found a path whose cost is guaranteed to be the lowest possible.
  - It ignores unsearched nodes with worse heuristic estimates because those estimates are guaranteed to be less promising than the path already found.

## Informedness
- When one heuristic is better the another?
$$
h1(x) <= hStar(x)
$$
$$
h2(x) <= hStar(x)
$$
$$
h1(x) <= h2(x) <= hStar(x)
$$
- h2(x) is more informed (i.e. better h1(x))
- Example (we can use and h(x) > 0 in the 8 puzzle game)
  - by setting h(x) = no.of tiles out of place
  - because we will need this number of moves or more h(x) is still optimistic
- Complexity issue
  - Simple heuristic. Quick to calculate heuristic. But doesn't prune much - huge space to search.
  - Good heuristic. Cuts space. But calculating heuristic takes time.
  - Trade-off - Find middle point where computational cost of problem solving is lowest. 

## Beam serach

- reduce the space to search with best first search 
- we do this by keeping a fixed size open list
- only keeping the n most promising (according to h(x)), unvisited state on OPEN
