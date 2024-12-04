---
date: 2024-12-03 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|advanced]]"
---

# State space search


## State Space Representation
- Represents all possible *states* of a system as nodes in a graph.
- *Actions* that move between states are represented as links.
- *Goal*: Find a *solution*, which could be:
  - Any path from the start state to the goal state.
  - The best path (e.g., lowest cost path, as in the Traveling Salesman Problem).


## Search Techniques
1. *Backtracking (Exhaustive Search)*:
   - Tries all possible paths until a solution is found.
   - Two main methods:
     - *Depth-First Search (DFS)*:
       - Explores deeply along a path before backtracking.
       - Uses less memory but may get stuck in unpromising branches.
     - *Breadth-First Search (BFS)*:
       - Explores all nodes at one level before moving deeper.
       - Requires more memory but guarantees the shortest path.

2. *DFS Algorithm*:
   - Uses 4 lists:
     - *SL*: Current state path.
     - *NSL*: States discovered but not yet explored.
     - *DE*: States known to lead to dead ends.
     - *CS*: Current state.
   - Explores deeply and backtracks when no new states are available.

3. *BFS Algorithm*:
   - Uses 2 lists:
     - *OPEN*: States discovered but not yet explored.
     - *CLOSED*: States already explored.
   - Explores level by level.


## Comparison of Breadth-First Search (BFS) and Depth-First Search (DFS)

| **Aspect**                 | **Breadth-First Search (BFS)**                                        | **Depth-First Search (DFS)**                                    |
|-----------------------------|----------------------------------------------------------------------|-----------------------------------------------------------------|
| **Optimality**             | Guaranteed to find the shortest path to the goal.                    | Might find a goal deep in the structure but not the shortest path. |
| **Path Length**            | Stops when the first goal is found.                                  | May find multiple paths and compare their lengths.              |
| **Tree Growth**            | Not affected by unbounded tree growth (continues level by level).    | Tree might grow indefinitely unless bounded by a depth limit.   |
| **Memory Usage**           | Requires a large **OPEN** list to store all known but unsearched nodes at the current level. | Requires much less memory as it only tracks the current path and backtracking points. |
| **Branching Factor**       | Problematic with high branching factors since the **OPEN** list grows exponentially (\(B^n\) nodes at level \(n\)). | Handles high branching factors better due to lower memory usage. |
| **Goal Depth**             | Best if the goal is relatively shallow in the state space.           | Best if the path to the goal is long, as it gets deep quickly.  |
| **Efficiency in State Space** | Can be slow for deep goals with many shallow nodes.                | Quick to reach deep states but might miss the optimal solution. |
| **Use Case**               | Good for small problems or goals close to the start.                 | Good for problems with deep solutions or limited memory.        |
| **Example**                | Not feasible for games like Chess due to the high branching factor.  | Often used in problems requiring deep exploration, like mazes.  |

## Iterative Deepening Depth-First Search (IDDFS)

*Iterative Deepening Depth-First Search (IDDFS)* is a search algorithm that combines the advantages of *Depth-First Search (DFS)* and *Breadth-First Search (BFS)* while overcoming their limitations:

- *How it works*:
  - Performs a depth-first search (DFS) with a maximum depth limit (e.g., 1 level).
  - If the goal is not found, increases the depth limit by 1 and repeats the search.
  - Continues increasing the limit until the goal is found.

- *Advantages*:
  - Finds the shortest path (like BFS) by exploring all levels of depth step by step.
  - Uses less memory (like DFS) as it only tracks one path at a time.
  - Ideal for very large or infinite search spaces, where BFS would require too much memory, and DFS might never stop.
