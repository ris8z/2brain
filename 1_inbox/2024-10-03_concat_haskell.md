---
date: 2024-10-03 
tags: 
    - haskell
hubs: 
    -   "[[2024-10-01_Haskell_Tutorial|haskell_Tutorial]]"
---

# concat_haskell

`concat :: [[a]] -> [a]` 

It takes a list of lists `([[a]])` and flattens it into a single list ([a]).

# Exmample

```haskell
main = do
    let listOfLists = [[1, 2], [3, 4], [5]]
    print (concat listOfLists)
```
this will be the output

`[1, 2, 3, 4, 5]` 

