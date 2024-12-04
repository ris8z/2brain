---
date: 2024-12-03 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|advanced]]"
---

# Tree search

## What is Tree Search?
- A method to structure the search space in AI problems.
- The search space is organized as a *tree* with:
  - *Parent nodes*: Represent the current state.
  - *Child nodes*: Represent possible next states or actions.
  - Example: In chess, the parent is the current board, and children are possible next moves.

## Applications
- Used in many problems, not just games.
- Example: *Tic-Tac-Toe*:
  - Parent: Current board.
  - Children: All possible moves.


## Binary Trees
- A *binary tree* is a special tree with:
  - Each node having *0 to 2 children*.
  - Useful for *ordering data*.
- *Binary Search Trees*:
  - Add data in a way that maintains order.
  - Search quickly by eliminating parts of the tree.


## Do We Have to Draw the Tree?
- *No*, the tree doesn’t need to be drawn.
  - It’s a *data structure* of nodes and links.
  - Visualization is only used for *debugging*.

- *Do We Need to Fully Define the Tree?*
  - No, you don’t need to predefine all nodes.
  - Nodes are calculated *on demand*, when they are needed.
  - Example: In chess, calculate the possible next moves *only when exploring that state*.
  - Many nodes might never be created (e.g., trillions of chess positions).


## Summary
- *Tree Search* helps systematically explore possible solutions.
- *Efficiency*: Only explore nodes when necessary.
- *Flexibility*: Works for games, optimization, and many AI problems.


