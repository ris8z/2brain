---
date: 2024-12-05 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|Advanced Algorithms and AI Search]]]"
---

# Machine evolution and Genetic Algorithm

## Introduction to Computational Evolution

- Natural evolution is a process that has created all known intelligence.
- Genetic Algorithms (GA) model evolution as an "algorithm" to solve problems.
- Two main approaches:
  - **Traditional Genetic Algorithms:** Based on fitness and selection.
  - **Artificial Life:** Creation of complex systems and observation of emerging strategies.

## Genetic Algorithms (GA)

### Basic Definition
- A GA seeks optimal solutions by imitating natural evolution.
- Operates through iterations of generations of "creatures" with "DNA" representing potential solutions.

### Structure of a GA
1. **Initialization:** Start with a random population.
2. **Main Loop:**
   - Evaluate the "fitness" of each creature.
   - Select the fittest individuals for reproduction.
   - Create a new generation through:
     - **Cloning:** Direct copy of DNA.
     - **Mutation:** Small random changes in DNA.
     - **Crossover:** Combination of genes from two parents.
   - Replace the old population with the new one.

### Key Elements
- **Genotype:** DNA representing the parameters of the solution.
- **Phenotype:** The "creature" built from the genotype that addresses the problem.
- **Fitness:** Measure of how well a solution solves the problem.

### Selection
- **Simple Method:** Only the top \( n \) individuals reproduce.
- **Probabilistic Method:** Probability proportional to fitness using:
  - Simple summation of fitness.
  - **Boltzmann "Softmax" Distribution** for balancing probabilities.

### Mutation and Crossover
- Small mutations to avoid drastic jumps.
- Crossover enables unique combinations, often "cutting" the genotype bitstrings.

## Encoding the Genotype

- **Binary Strings:**
  - Each genotype is a sequence of 0s and 1s.
  - Decoded into real numbers, integers, or text.
- **Gray Codes:** Minimize drastic jumps in the adaptive landscape.
- **Bitstrings vs. Direct Parameters:**
  - **Bitstrings:** Universal but less flexible.
  - **Direct Parameters:** Specific but more intuitive for certain applications.

## Adaptive Landscape

- Fitness represents a multidimensional landscape.
- GAs use a population of solutions to explore different areas of the landscape.
- Challenges:
  - **Local Maxima:** Can block evolution.
  - **Barriers:** GAs can overcome them through crossover or random mutations.

## Boltzmann Distribution

- Used to balance reproduction probabilities.
- **Temperature (T):**
  - **High T:** Similar probabilities for all creatures.
  - **Low T:** Favors creatures with higher fitness.
- **Practical Considerations:**
  - Avoid \( T = 0 \) or extremely high/low fitness values to prevent overflow errors.

