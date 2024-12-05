---
date: 2024-12-05 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|advanced Algorithms and AI Search]]"
---

# Types of learning

## Supervised Learning

- Requires a *teacher with labeled exemplars* (input-output pairs).
- Focused on learning the correct output for given inputs.
- Limitation: Relies heavily on large labeled datasets, which is not how humans/animals usually learn.

## Reinforcement Learning (RL)
- Learning happens through sporadic *rewards and punishments*, not explicit answers.
- Rewards are numeric and the goal is to maximize cumulative rewards over time.
  - Example: Robot soccer:
    - +10 points for scoring a goal.
    - -10 points if the opposition scores.
- Trial-and-error methods are used to "grade" actions in specific states.
- Neural networks in RL can generalize behavior rather than just classify inputs.
- Applications:
  - *Robotics* (e.g., teaching a robot to walk).
  - *Games* and decision-making systems.

## Unsupervised Learning
- Focuses on dividing input space into categories without labeled exemplars.
- The aim is to *learn patterns and groupings in the data*. (*no labled exemplars*)
  - Examples:
    - Grouping countries with similar economies.
    - Compressing data using neural networks like autoencoders:
      - Input is encoded into fewer hidden nodes and reconstructed.
      - Efficient representation of data, unlike a simple lookup table.
  - Applications:
    - *Data compression* (learning adaptive compression methods).
    - *Clustering* (e.g., Facebook’s SEER algorithm sorts images into categories without labels).
- Simple Pseudo algorithm
  1. input $x$.
  2. run through networks to get output $y$.
  3. compare $y$ with $x$. 
  4. backpropagate the $\text{Error} = \|x - y\|$

## Convolutional Neural Networks (CNNs)

- Designed for 2D pattern recognition (e.g., image recognition).
- Efficiently *learns patterns across shifted positions in input*.
  - Example: Recognizing a face in different parts of an image without relearning the pattern.
- Application:
  - *Image and video recognition*.
  
## Recurrent Neural Networks (RNNs)

- **Vanilla NeuralNetworks (FeedForward)**
  - data flow is *unidirectional* goes from input to output

- **Recurrent Neural Networks (FeedBack)**
  - data flow *is not unidirectional* thanks to feedback loops 
  - Includes *feedback loops* for processing *sequential or continuous data*.
  - Applications:
    - *Speech recognition*
