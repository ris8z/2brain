---
date: 2024-12-04 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|Advanced Algorithms and AI Search]]"
---

# Machine Learning   Introduction

## Definition
- *Machine Learning* program imporves over time, over repeated learing interactions.
- It is not just Memorize but it is also capable of *generalise* new output for unseen input.
  - I. E.
    - Human:		In situation x1, answer is a1.
    - Human:		In situation x2, answer is a2.
    - Human:		In situation x3, answer is a3.
    - Human:		In situation x4, what is answer?
    - Machine:	f(x4).
    - where the machine is "learning" the function f.
- The goal of our Machine si to plot (rappresnt) a function from the data the we feed to it.

## Key concepts 
- *Exemplars*
  - Input-Output pair (xi, ai) used to lear a funciton f
- *Supervised Learing*
  - Learing a function f by providing exemplers as training data
- *Interpolation*
  - Predict within the range of provided exemplars 
  - I.E. if f(0) = 0 and f(100) = 100 predic f(50)
- *Extrapolation*
  - Predict outside the range of provided examplars
  - I.E. based on f(0) = 0 and f(100) = 100 predict f(150)
- *Linear Regression*
  - In statistc we can polt a function from data using Linear regression
  - the goal is to find an equation that describe the data

## Goal
- *The goal of a ML program* is to rappresent a fuction without an eqution but using:
  - data strucure
  - algorithms
- *Best target* (nearby input -> nearby output)
  - reasonably well behaved non-linear, continuous ,non chaotic function.
- *Mid target*
  - discontinus function (like learning the capital of the word)
  - learing is not possible, only Memorize is possible
  - interpolation not possible (you can not say the capital of france is Lond-Rome bc is between italy and uk)
- *Worst target*
  - Chaotic functions
- *Whis list*
  - an alogrithm that learn which input are important
  - Not like in the ex of sad/happy faces (using Hamming Distance)

## Neuarl network
- It is the answer to our wish list because:
  - can represent a function *f* from exemplars multi-dimensional input -> multi-dimensional output,
  - can *learn* a general *non-linear, continuous, non-chaotic function*
  - can learn which parts of the input are important and which are not (*can weigh input dimensions differently*),
  - can remove entirely parts of the input that are not important (*set weight to zero*),
  - can build up the representation *from scratch* based only on seeing exemplars,
  - can do this in a *fixed-size* data structure, 
  - can return an answer *quickly* to a given input without having to examine every past exemplar
  - can return an answer in a *finite time* (in fact, in exactly the same time for all inputs), 
  - can return an answer for inputs never seen before. (*prediction*)
  - represent a behaviour-generating module from the start .(*works from the start*) 
