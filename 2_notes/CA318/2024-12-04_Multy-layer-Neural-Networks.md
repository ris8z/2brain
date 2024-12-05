---
date: 2024-12-04 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|Advanced Algorithms and AI Search]]"
---

# Multi-layer Neural Networks

## Multi-layer (hidden nodes)
- Multi-layer Neural Networks allow
  - much more complex classifications. 
    ![alt text](https://humphryscomputing.com/Notes/Neural/Bitmaps/multi.howto.jpg) 
- In fact we can finally design a XOR network using 3 perceptrons
    - 2 perceptrons just pass the signal (up and down)
    - 1 perceptrons is an and gete like (the middle one)
    - suppose the only input we can have are 0 or 1
    ![alt text](https://humphryscomputing.com/Notes/Neural/Bitmaps/multi.xor.jpg)  

## No more design of Neural Networks

- Instead of manually designing networks like the XOR network, we want the network to learn the weights and thresholds on its own.
- By using suprevised learing

## Supervised Learning
- Presenting an input (x) to the network.
- Running the input through the network to produce an output (y).
- Providing the network with the correct answer for x (the ground truth).
- Comparing y with the correct answer to calculate an error.
- *Adjusting the weights and thresholds using this error to make the output closer to the correct one next time.* (this one is hard)

## Interfence both problem and solution
- because when we are modifing the weight and trashold, to get one solution better we may lose another one
- but the interefenece is what we want to be able to generate solution for unseen input.

## Sigmoid activation function
- it is just a function that squeze the weighted sum into a value between 0-1
$$
\sigma(x) = \frac{1}{1 + e^{-x}} = y
$$
- in this approach the tresh hold is impled in the weighted sum as basis b (a negative number like -10)
$$
w_k = \sum_{k=1}^{n} I_k w_k + b_k
$$
- this baias rappresnt just how likly a neuor is to be active
- its derivative is equal to $y (1 - y)$
