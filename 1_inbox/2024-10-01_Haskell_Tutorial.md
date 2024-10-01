---
date: 2024-10-01 
tags: 
    - video
urls:
    - https://youtu.be/02_H3LjqMr8?feature=shared`
---

# Haskell_Tutorial

### Context:

Haskell is a *functional* programming language
Every thig in it is *immutable*
*Recursion* is used very often
Haskell is also *lazy* it dosen't execture more than it is needed
It is a *complied* language
It is *staicly-typed*, it also uses *type-Inference*

### Why using Haskell?
The 3 most powerfull part of haskell by david sincaler
- High order function (bc it's really good with parallel programming ex: Google search engine)
- Patter matching, (bc the code is smaller and readable)
- Recursion 

### Comments:

```haskell
-- this is an inline comment
```

```haskell
{-
this is a multi lines comment
-}
```

### Important Modules

```haskell
import Data.List
import System.IO
```

### Date Types

- Int  (between -2^63 -- 2^63)

- Integer (without Bound)

- Float

- Double

- Bool

- Char (denoted by `'` like in C)

- Tuple (it contains two values)

### Math functions:

```hasell
addEx = 5 + 3
subEx = 5 - 4
multEx = 5 * 3
divEx = 5 / 4 --gives u a float

modEx = mod 5 4
modEx2 = 5 `mod` 4
integerDiv = 5 `div` 3

-- weird things:
negNumEx = 5 + (-3)

num9 = 9 :: Int
sqrtOf9 = sqrt (fromIntegral num9)

-- built in function
piVal = pi
ePow9 = exp 9
logOf9 = log 9
squared9 = 9 ** 2
truncateVal = truncate 9.999
roundVal = round 9.999
ceilingVal = ceiling 9.999 -- always round up
floorVal = floor 9.999 --- always rounding down
```
> [!TIP]
*Python* round(): Rounds to the nearest integer, and if the number is exactly halfway (like x.5), it *rounds away from zero* (e.g., 2.5 rounds to 3, -2.5 rounds to -3).
> 

> [!TIP]
*Haskell* round: Rounds to the nearest integer, but if the number is exactly halfway (like x.5), it *rounds to the nearest even number* (this is known as bankers' rounding).
> 

### Logic Opereor

```haskell
trueAndFalse = True && False
trueOrFalse = True || False
notTrue = not(True)

```

### List
```haskell


-- cool things:
newList = [1..10]
evenList = [2,4..20]
sumOfNums = sum[1..1000]
prodOfNums = product [1..3]
letterList = ['A','C',..'Z']
```
