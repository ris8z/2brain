---
date: 2024-12-18 
tags: 
    - CA341
hubs: 
    -   "[[2024-12-18_Comparative-Programming|Comparative Programming]]"
---

# Functional Programming

- Computation = evaluation of expressions.
- **Key concepts**:
  - Referential *transparency*
  - *Higher-order* functions
  - *Recursion*
  - *Lazy* and *strict* evaluation
    - ```haskell
        -- Lazy Evaluation: Expressions evaluated only when needed.
        infiniteList = [1..]
        take 5 infiniteList -- Only uses first 5 element

        -- Strict Evaluation: Expressions evaluated immediately. Example in 
        let square x = x * x
        let result = square (3 + 4) -- (* Result: 49 *)
      ```
  - *Currying* (f with multiple agrs is transofrm into a sequence of fs with a single arg)
    - ```haskell
        multiply :: Int -> Int -> Int
        multiply x y = x * y

        double = multiply 2
        double 4   -- Result: 8
      ```
  - *Polymorphic type systems*
- **Reasons for using it** :
  - *Predictable* and testable code
  - *Ease* in *concurrent* programming
  - Popular for data analysis, AI, and more

