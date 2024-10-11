---
date: 2024-10-06 
tags: 
    - backtrack
hubs: 
    -   "[[2024-10-05_subset|subset]]"
---

# combinations_disposition_permutation

Un po di chiarezza matematica abbiamo solo:

## Diposizioni
- ordine conta
- niente ripetizioni

### Semplici
Servono per contare in quanti modi si possono prendere K elementi da un insieme di N elementi
$$
D_{n,k} = \frac{n!}{(n-k)!}
$$

### E non (permutazioni)
Se K e N sono uguali, vengono chiamate permutazioni
$$
P_{n} = D_{n,n} = \frac{n!}{0!} = n! 
$$

----------


## Combinazioni
- ordine non conta
- niente ripetizioni

Servono per contare in quanti modi si possono prender K elmenti da un insieme di N elementi senza contare l'ordine
$$
C_{n,k} = \binom{n}{k} = \frac{n!}{k!(n-k)!} = \frac{D_{n,k}}{k!} = \frac{D_{n,k}}{P_{k}}
$$

> [!TIP]
> Le combinazioni non solo altro che le combinazioni divise per k! = Permuatzaione di k (il numero di modi in cui puoi ordinare gli elementi)
appunto perche' l'ordine non conta

## Combinazioni con ripetizioni
- ordine non conta
- gli elementi si possono ripetere
$$
C_{\text{rep}}(n, k) = \binom{n + k - 1}{k} = \frac{(n + k - 1)!}{k!(n + k - 1 - k)!}
$$

----------

## Esempio

Definiamo n e k
$$
n = 5, k = 2
$$

Disposizione (tutti i modi in cui posso prendere 2 elementi da una lista di 5) (ordine conta, no ripetizioni)
$$
D_{5,2} = \frac{5!}{(5 - 2)!} = 5 * 4 = 20
$$

Combinazioni (tutti i modi in cui posso prender 2 elementi da una lista di 5) (ordine non conta, no ripetizioni)
$$
C_{5,2} = \frac{D_{5,2}}{2!} = \frac{20}{2} = 10
$$

### shokkante
se k=2 (1,2),(2,1) quindi devi dividere per 2! = 2
se k=3 (1,2,3),(3,2,1),(3,1,2),(1,3,2),(2, 3, 1),(1,3,2),
QUINDI
(Disposizioni Semplici) = (Numero di opzioni uniche) * (quante Copie ne posso avere se ne cambio l'orinde)
(Disposizioni Semplici) = Disposizione(n,k)
(Numero di opzioni uniche) = Combinazione(n,k)
(quante Copie ne posso avere se ne cambio l'orinde) = "visto che la dimensione delle opzioni uniche e' k" e' esattamente la definizzione di permutazione di k = k!

$$
D_{n,k} = C_{n,k} * P_{k}
$$

## Codice
### Disposizioni intuizione

![[disposizioni.png]]

### Code
```python3
from typing import List

#O(numero di disposizione * per altezza del tree)
#O(D_{n,k} * k)
#case peggiore k = n --> O(D_{n,n} * n) --> O(n! * n)
#ma in realta e' diffcult capirlo

def dis(nums: List[int], k: int) -> List[List[int]]:
    result: List[List[int]] = []
    buffer: List[int] = []
    visited: List[bool] = [False] * len(nums)

    def dfs():
        if len(buffer) == k:
            result.append(buffer.copy())
            return

        for idx, val in enumerate(nums):
            if visited[idx]:
                continue

            buffer.append(val)
            visited[idx] = True
            dfs()

            buffer.pop()
            visited[idx] = False
    dfs()
    return result

nums = list(range(1,6))
k = 2
print(dis(nums,k))

```

----------

### Combinazioni intuzione

![[combination.png]]

### Code O(k*(2**n))
```python3
from typing import List

def comb(nums: List[int], k: int) -> List[List[int]]:
    result: List[List[int]] = []
    buffer: List[int] = []
    def dfs(i: int) -> None:
        if len(buffer) == k:
            result.append(buffer.copy())
            return

        if i >= len(nums):
            return
        
        n: int = nums[i]
        #all the combination with n
        buffer.append(n)
        dfs(i + 1)

        #all the combination without n
        buffer.pop()
        dfs(i + 1)

    dfs(0)
    return result

nums = list(range(1,6))
k = 2
print(nums, k)

print(comb(nums,k))

```

### Imporved version from neetcode

![[Pasted image 20241006212309.png]]

### Code
```python3
# O(k * C(n,k))
def improved(nums: List[int], k:int) -> List[List[int]]:
    result: List[List[int]] = []
    buffer: List[int] = []
    def dfs(i: int) -> None:
        if len(buffer) == k:
            result.append(buffer.copy())
            return
        
        if i >= len(nums):
            return


        for j in range(i, len(nums)):
            n: int = nums[j]
            buffer.append(n)
            dfs(j + 1)
            buffer.pop()

    dfs(0)
    return result
```
----------

## Esercizi dopo/domani

- Combination
    [leetcode](https://leetcode.com/problems/combinations/) 
    [solution](https://github.com/ris8z/leetcode/blob/main/BackTrack/combinations.py) 
