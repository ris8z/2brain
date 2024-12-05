---
date: 2024-12-05 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|Advanced Algorithms and AI Search]]"
---

# Deep Learning and ReLu function

## Deep Learing
- they are neaural networks with many hidden layers

## How to calculate?
- all this calculation from the backprogagation algorithm.
- are well suited to be done in parallel hardware GPUs.

## ReLu function
![alt text](https://humphryscomputing.com/Notes/Neural/Images/5.png) 
$$
\text{ReLU}(x) = \max(0, x)
$$

- deep learing discored an issue with sigmoid f(x)
- a much simpler activetion f(x) is better one such as **ReLu function**

- **Properties**:
  - Slope is 0 below x=0.
  - Not differentiable at point x=0
  - Slope is constant for x above 0
- **Impact on neural network learning**:
  - Using this activation function vastly *increases the number of neurons outputting zero* for a given input. Meaning these neurons can be entirely ignored by the next layer (as opposed to a system where almost all neurons are in play, even if only by a small amount).
  - This leads to what is called "sparse representations" and makes very large networks *computationally practical*.
  - It is much *faster* to calculate than sigmoid. Very important for scaling.

