---
date: 2024-12-09 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|Advanced Algorithms and AI Search]]"
---

# Support Vector Machine (SVM)

## What they are?
- SVM are a type of *supervised machine learning alogrithm*
- used for:
  - *Text classification*: Spam detection, sentiment analysis.
  - *Image recognition*: Face detection.
- SVM are particularly *powerful for binary classification* problems 
- but can be *extended to multi-class* scenarios as well.

## Key Idea
- rappresent data as a *point* into a multidimentional space using *vectors*
- find the best *decesion boundary (HyperPlane)* that splits data point of different classes in a multidimentional space.
- the goal is to *maximize the margin (distance)* between the *hyperplane* and the *nearest data points* from each classes, which are called *support vectors*

## Key components
- *Hyperplane*
  - a *line* in 2d a plane in 3d or a higher dimension equivalent
  - 2d example:
    - $w * x + b = 0$
    - $w$ -> weight vector
    - $x$ -> featurs (input) vector
    - $b$ -> baias
- *Margin*
  - distance between the hyperplane and the nearest data point of each class
  - SVM maximize this margin to *ensure* that the model generlizes *well on unseen data*
- *Support Vectors*
  - data points closest to the hyperplane.
  - they are *important* to define the *position and orientation* of the *hyperplane*

## Types of Support Vector Machine
- *Linear*
  - when the data is *linearly separable*
- *Non-Linear*
  - when the data is *not linearly separable* to fix this issue it use the *Kernel trick*

## How to handle more classes? 
- lets pretend that we need to recognize 3 faces (Anna, Mario, Lorenzo)
- Two diffenet approach
  - **1 vs 1**
    - *How?*
      - we build a SVM for each class cuple possible
        - SVM1: Anna vs Mario
        - SVM2: Anna vs Lorenzo
        - SVM3: Mario vs Lorenzo
      - we data arrives, each SVM define if it is more of a class or another 
      - the final result is the one that wins more conflict
    - *pro*
      - very accurate
    - *issue*
      - a lot of SVMs $(n \times (n - 1) / 2)$
  - **1 vs All of them**
    - *How?*
      - we build one SVM for each class, confronting it with all the other classes
        - SVM1: Mario   vs (Anna + Lorenzo).
        - SVM2: Anna    vs (Mario + Lorenzo).
        - SVM3: Lorenzo vs (Mario + Anna).
      - we data arrives, each SVM evaluate a number for its class, we pick the higher number
    - *pro*
      - less SVM just $n$
    - *issue*
      - can be less accurate
