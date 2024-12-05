---
date: 2024-12-05 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|advanced Algorithms and AI Search]]"
---

# BackPropagation learning alogrithm

## Simple explnaion

- This is the heart of a neaural networks
- it comes down just to minimase a creatian function
- that function is a cost/error heuristc function
- To simplify things up let's pretend this function is in 2d 
  - (in reallity it is in Nd)
  - (and we are not talking about slope but gradient)
- with weight as x and error/cost as y
- we can use the slope to guide as into a local minum
- kinda like a ball that goes down on the hill
- so if the slope is positive, we make a samll aggustment to the left
- so if the slope is negative, we make a samll aggustement to the right
- this aggustment are propotial to the slope se while we are getting closer and closer to the minimu
- slope = 0, also our steps get smaller, this prevent overshooting.

## The alogorithm

1. send input to the function
2. get the outputs back *y*
3. get given correct output *o*
4. from *o* and *y* evaluate the Cost functinm *E* 
5. for each weight
  - evaluate the slope of the cost function
  - update the weight
  - w = w - C * (slope)
  - (slope) is the partial derivative of E in respect of w
6. reapet

## How to find the slope and the partial derivaties?
- see on the scap book orange page in the end part
- it is not that bad after you get the math

## It is Heuristic
- Backpropagation is a heuristic for training multi-layer neural networks by minimizing error through gradient descent.
- It adjusts weights based on error slopes but cannot guarantee finding the global minimum, often settling in local minima.
- Noise (e.g., stochastic gradient descent) helps escape local minima.
  - poor words add a bit of the random in the step while chaneing the weights
  - benefits
    - you may exit a flat zone or a local optimu
    - specialization may different part of the system spcilizy on different patterns
  - risk
    - may prevent convergence, causing the model to diverge
  - Outcome
   - maybe use it at start to explore and gradually reduce the noise
- Backpropagation's outcomes depend on initial weights, and no convergence proof exists for multi-layer networks.
  - means: you cant prove that this system will lear to separte exemplers (like in the perceptrons)
- It’s widely used despite its limitations, as exhaustive weight searches are computationally impractical.
