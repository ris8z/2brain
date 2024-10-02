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
notequalto = True /= False
notTrue = not(True)

```

### List
```haskell
--Haskell list are linkedlist so appeding, or concatention to it takes O(n)
--while adding in the front prepeding is just 0(1)


-- list inside list
multiList = [[1,2], [3,4]]

-- prepending O(1)
lst = 2 : 4 : 8 : []
anotherLst = 1 : lst

-- concatentaion of a list O(n)
a = [3, 4, 5, 6, 7, 8, 9]
b = [1, 2] ++ a
c = a ++ [6, 7]

-- len of a list O(n)
lanA = length a

-- Reverse a list O(n)
reverseA = reverse a

-- Is a list empty O(1)
isAEmpty = null a

-- get from the index an element O(n)
secondElement = a !! 1

-- get the first element
firstElement = head a

-- pop the first element
tailA = tail a

-- get the last element
lastElement = last a

-- pop the last element
aInit = init a

-- get the first n element
first3a = take 3 a

-- remove the first 3 element
removedA = drop 3 a

-- check if an elment is in a list
is7inA = 7 `elem` a

-- get the max and min
maxA = maximum a
minA = minimum a

-- cool things:
oneToTen = [1..10] -- 1,2,3,ecc
evenList = [2,4..20] -- 1,2,4,6
sumOfNums = sum[1..1000]
prodOfNums = product [1..3]
letterList = ['A','C'..'Z'] --A, C, E, G
many2s = take 5 (repeat 2) -- [2,2,2,2,2]
many3s = replicate 5 3 --    [3,3,3,3,3]
cycleList = take 10 (cycle [1,2,3,4,5]) -- [1,2,3,4,5,1,2,3,4,5]
listTimes2 = [x * 2 | x <- [1..3], x * 2 < 5] -- [1,4]
-- you can go crazy like finding all the number divisble both from 13 and 9
divby13and9 = [x | x <- [1..500], x `mod` 13 == 0,x `mod` 9 == 0]

-- sorted list
sortedList = sort [9,23,3,2,1,12]

-- zip function
sumOfLists = zipWith (+) [1,2,3] [1,2,3]

-- filter
biggerThan5 = filter (>5) a

-- takeWhile with infinity list
evensUpTo20 = takeWhile (<=20) [2,4..]

{-
foldl e foldr sono utilizzate accumulare una lista in un singolo valore
applicando una funzione binaria agli elementi della lista,
insieme a un valore iniziale.

La differenza principale tra le due sta nella direzione in cui attraversano la lista:
    foldl (fold left): elabora gli elementi della lista da sinistra verso destra.
    foldr (fold right): elabora gli elementi della lista da destra verso sinistra.
-}
foldlist = [1,2,-3,4,5]
fl = foldl (*) 1 foldlist
fr = foldl (8) 1 foldlist

```

### Tuple

```haskell
t = (1, "a")
me = ("giuseppe", 21)
name = fst me
age = snd me

names = ["giuseppe", "mario", "marco"]
ages = [21, 18, 19]
names_and_ages = zip names ages -- [("giuseppe",21),("mario",18),("marco",19)]
```

### Function
- Main function:
```haskell
import Data.List
import System.IO


main = do
    putStrLn "what is your name?"
    name <- getLine
    putStrLn ("hello " ++ name)

```

> [!TIP]
> you can create a bin file of this by `ghc --make filename.hs` 
or just load the file in ghci with `:load filename.hs` and type `main` 

- Function prototype
```hasell
-- funcName :: typeFirstPartm -> typeSecondParm -> typeReturned
-- funcName param1 param2 = operations (returned value)
```
> [!WARNING]
> function can not begin with Upper case latter 

* Function exmaples
```haskell
addMe :: Int -> Int -> Int
addMe x y = x + y

addTuples :: (Int, Int) -> (Int, Int) -> (Int, Int)
addTuples (x, y) (x2, y2) = (x + x2, y + y2)

factioral :: Int -> Int 
factioral 0 = 1
factioral n = n * factorial(n - 1)
```

### Guards
```haskell
isEven :: Int -> Bool
isEven x 
    |   x `mod` 2 == 0 = True
    |   otherwise = False

whatGrade :: Int -> String
whatGrade age
    |   (5 <= age) && (age <= 10) = "Elementari"
    |   (11 <= age) && (age <= 13) = "Medie"
    |   (14 <= age) && (age <= 19) = "Superirori"
    |   (20 <= age)  = "Probabilmente disoccupato"
    |   otherwise = "malo kid"
```

### Where
```haskell
ratingRATEO :: Int -> Int -> String
ratingRATEO kill death
    |   avg <= 0.9 = "pretty bad"
    |   avg <= 1.2 = "average player"
    |   avg <= 1.5 = "good player" 
    |   avg <= 1.8 = "aim demon" 
    |   otherwise = "you should go pro tenz fears u"
    where avg = fromIntegral kill / fromIntegral death
```

### (x:xs) pattern matching
 ```haskell
--Easy example
getListItems :: [Int] -> String
getListItems [] = "Your list is empty"
getListItems (x:[]) = "Your list is made by just one element " ++ show x
getListItems (x: y: []) = "Your list is mady by just two elements " ++ show x ++ " " ++ show y
getListItems (x:xs) = "Your list start with " ++ show x ++ " and continue with " ++ show xs

--String equal with recursion and (x:xs) pattern matching
areStringEqual :: String -> String -> Bool
areStringEqual [] [] = True
areStringEqual (x:xs) (y:ys) = x == y && areStringEqual xs ys
areStringEqual _ _ = False -- _ _ is all the other combination i dont care
-- we can cover the other two cases with this line above
--  areStringEqual [a] [] = False
--  areStringEqual [] [a] = False
 ```

### all@ keyword
```haskell
getFirstChr :: String -> String
getFirstChr all@(x:xs) = "the first letter in " ++ all ++ " is " ++ [x]
```

> [!TIP]
> is u use show x u get the whole list like: [x], if u want to print just x
just use ++ [x] so u use concatenation e u get one final string to print


### Map and High order functions
```haskell
-- just means that function can be used as normal var

times4 :: Int -> Int
times4 x = x * 4
listTimes4 = map times4 [1,2,3,4,5] -- [4,8,12,16,20]

--Take a function as a argmuent (how does map work)

newmap :: (Int -> Int) -> [Int] -> [Int]
newmap f [] = []
newmap f (x:xs) = f x : newmap f xs
listTimes4Again = newmap times4 [1,2,3,4,5] -- [4,8,12,16,20]

-- (Int -> Int) -> [Int] -> [Int]
--  this line means that our newmap function is expecting two arguments
--      (Int -> Int) a function that takes an int and return and int
--      [Int] a list of interger
--  and returning
--      [Int] a list of integer
--  Ez.

--Returing a function
getAddFunc :: Int -> (Int -> Int)
getAddFunc x y = x + y

add3 = getAddFunc 3
fourPlus3 = add3 4
--Int -> (Int -> Int)
--  this means that the function takes as parmater an integer (that we labal with x)
--  and return a function that takes itself an integetr as paramter (that we label with y) and return, the x + y function
--  where x is a constant 3 in these case, and y is the variable
```

## Lambda function (function with no name)
```haskell
-- exmaple:
-- \x -> x + 1
doubleTo101 = map (\x -> x * 2) [1..10] -- [2,4,6,8,10,12,14,16,18,20] 
```
## if statment expression
```haskell
--they are just expression so after the then and else u need to put the retourn value
doubleEvenNumber :: Int -> Int
doubleEvenNumber x =
    if (x `mod` 2 /= 0)
        then x
        else x * 2
--so it's not if that execute this block of code, is if that return this value
```

## Case (it's just a switch statement like expression) 
```haskell
state :: Int -> String
state x = case x of
    1 -> "the light is on"
    0 -> "the light is off"
    _ -> "the light is funcking bugged"
```

min 57.8

