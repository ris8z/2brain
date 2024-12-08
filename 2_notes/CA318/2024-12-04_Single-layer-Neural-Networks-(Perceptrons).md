---
date: 2024-12-04 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|Advanced Algorithms and AI Search]]"
---

# Single layer Neural Networks (Perceptrons)

## The Perceptron

![[Pasted image 20241204190620.png]]
- Input nodes (or unit) are connected (typically full) to a node (or multiple nodes) in the next layer.

- x = $(I_1, I_2, \ldots, I_n)$
- w = $(w_1, w_2, \ldots, w_n)$
- *The Perceptron* apply the summation to all his inputs and weights and then reutrn the step function of the summation. 
- *Summation*

$$
\sum_{i=1}^{n} w_i \cdot I_i
$$

- *Step Function*

$$
\text{if} \sum_i w_i I_i \geq t \text{ then } y = 1 \\
$$

$$
\text{else (if } \sum_i w_i I_i < t\text{) then } y = 0
$$

- *Outcome*
  - let's consider just a 2-dimension input 
  - $x = (I_1, I_2)$
  - $w = (w_1 = 1, w_2 = 1)$
  - $t = 2$
  - $(\sum_{i=1}^{n} w_i \cdot I_i = I_1 + I_2 )<= 2$
![[Pasted image 20241204192613.png]]
  - all the point greater than line $I_1 + I_2 = 2$ are going to fire 1 as output
  - Basically the perceptron draws a line that split the space in two part (in more dimension it draws an hyperplane)
    - one fires up 1
    - one firss up 0
- *Limitations*
  - not every set of points can be divided by a line like this. Those that can be, are called *linearly separable*. 
  - i.e. (XOR) (to proof this do a little system with the conditions and there is a contadiction)

## Perceptron Learning Rule
- Alogrithm:
  - take an input *$x = (I_1, I_2, \ldots, I_n)$*
  - get output y 
  - if *y == O*: do nothing
  - if *y != O*: 
    - update weights *$w_i := w_i + C \cdot (O - y) \cdot I_i$*
    - update trashold *$t := t - C \cdot (O - y)$*
  - reapt the process for all the inputs, until you get all the expected answer
- *O* is the expected output
- *(O - y)* is the error the differenze between expexted output and actual output
- *C* is some postive learning state (works kinda like that)
- *How we update weights and trashold?*
    - *if y=0 and O=1:*
      - then y is not large enough
      - so reduce threshold and increase wi's. This will increase the output. 
    - *if y=1 and O=0:*
      - output y is too large
      - so increase threshold and reduce wi's (where Ii=1). This will decrease the output.
