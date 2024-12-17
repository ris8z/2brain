---
date: 2024-12-17 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability & Complexity]]"
---

# Computability vs Complexity

## 1. Computability  
**Definition**: Computability determines if a problem can be solved by a computational process (e.g., a Turing machine) within a **finite amount of time**.

### Key Aspects of Computability  
- **Decidable Problems**:  
  Problems for which an algorithm exists that always terminates with the correct answer.  
  - Example: Determining if a string belongs to a regular language.  

- **Undecidable Problems**:  
  Problems for which no algorithm exists that solves the problem for all inputs.  
  - Example: **The Halting Problem** – determining if a Turing machine halts on a specific input.

### Summary:  
Computability sets the boundary of **what can and cannot be solved** using algorithms.

---

## 2. Complexity  
**Definition**: Complexity focuses on the **efficiency** of solving computable problems, i.e., how much time and space a solution requires.

### Key Aspects of Complexity  
1. **Time Complexity**:  
   - Measures how execution time grows as input size increases.  
   - Examples: $O(n)$,$O(n^2)$, $O(2^n)$.  

2. **Space Complexity**:  
   - Measures how memory usage grows with input size.  

3. **Complexity Classes**:  
   - **P**: Problems solvable in **polynomial time** (efficient).  
   - **NP**: Problems where solutions can be **verified** in polynomial time.  
   - **NP-Complete**: The hardest problems in NP.  
   - **NP-Hard**: Problems at least as hard as NP-complete problems (may not belong to NP).  

### Summary:  
Complexity classifies **how efficiently** a problem can be solved.

---

## 3. Relationship Between Computability and Complexity  

- **Computability is a prerequisite for complexity**:  
  A problem must first be computable before analyzing its efficiency.  
  - Example: Undecidable problems (like the Halting Problem) have no time or space complexity.

- **Efficiency matters**:  
  - **Sorting** is computable in polynomial time (efficient).  
  - The **Traveling Salesperson Problem** is computable but requires exponential time in general.

- **Boundary of Feasibility**:  
  Complexity helps distinguish:  
  - **Practical Problems**: Solvable in polynomial time (e.g., in $P$).  
  - **Intractable Problems**: Solvable but inefficient, requiring exponential or worse time.

---

## 4. Key Takeaways  
- **Computability**: Determines if a solution exists.  
- **Complexity**: Determines the efficiency of finding the solution.  
- Together: They define the theoretical **limits of computation**.
