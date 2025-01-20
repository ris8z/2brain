---
date: 2025-01-15 
tags: 
    - CSC1044
---

# ID3 algorithm

## Goal
create a model that can predict if you can play tennis based on the weather conditions
using a data table that is at the end of the page

## Entropy
$$
H(S) = - \sum_{i=1}^k p_i \log_2(p_i)
$$
Where
- $p_i$: probability of each class $i$ (e.g., "Yes" and "No" in our case).

It tell us how *unpredicatable is the data*
- Entropy can be:
  - *low*:
    - one outcome is much more likley then the other ones
    - so the data are more predictable
  - *high*:
    - all the outcomes is equally likley 
    - so the data are less predictable
  - *max*:
    - Entropy is maximum (highest uncertainty) when the classes are balanced (e.g., 50%-50%).

Example

- There are 14 total rows in the dataset: 9 with "Yes" and 5 with "No".
- $p(\text{Yes}) = \frac{9}{14}$
- $p(\text{No}) = \frac{5}{14}$
- $H(S) = - \left( \frac{9}{14} \log_2 \frac{9}{14} + \frac{5}{14} \log_2 \frac{5}{14} \right) \approx 0.94$


## Information Gained
$$
IG(A) = H(S)- I(A)
$$

Where
- $H(S)$ starting entropy before division
- $I(A)$ coditioned entropy after splitting the data based on a charaterstic A

$$
I(A) = \sum_{v \in A} p(v) \cdot H(v)
$$

Where:
  - $v$ dinstinct value of a class A (i.e. Sunny,Overcast,Rain) for class Outlook 
  - $p(v)$ n of rows with v / tot n of rows 
  - $H(v)$ Entropia del gruppo di righe con il valore vv.

It tell us how much the *entropy decrease* by splitting the data based on a *specific charateristic*


Example 

- Consideriamo la caratteristica *Outlook* con valori "Sunny", "Rain", "Overcast".
- we know *$H(S) = 0.94$*
- *split* the value of the class *Outlook*
  - Sunny: 5 row (2 "Yes", 3 "No").
  - Rain: 5 row (3 "Yes", 2 "No").
  - Overcast: 4 row (4 "Yes", 0 "No").
- evaluate *$H(v)$ and $p(v)$* for each value of the calss OutLook
  - Sunny:
    - $H(Sunny) = - \left( \frac{2}{5} \log_2 \frac{2}{5} + \frac{3}{5} \log_2 \frac{3}{5} \right) \approx 0.971$
    - Peso: $p(Sunny) = \frac{5}{14}$.
  - Rain:
    - $H(Rain) = - \left( \frac{3}{5} \log_2 \frac{3}{5} + \frac{2}{5} \log_2 \frac{2}{5} \right) \approx 0.971$
    - Peso: $p(Rain) = \frac{5}{14}$.
  - Overcast:
    - $H(Overcast) = - \left( \frac{4}{4} \log_2 \frac{4}{4} \right) = 0$
    - Peso: $p(Overcast) = \frac{4}{14}$.
- evaluate *$I(A)$*
  - $I(Outlook) = \left( \frac{5}{14} \cdot 0.971 \right) + \left( \frac{5}{14} \cdot 0.971 \right) + \left( \frac{4}{14} \cdot 0 \right) \approx 0.693$
- evaluate *$IG(Outlook)$*
  - $IG(Outlook) = H(S) - I(Outlook) = 0.94 - 0.693 \approx 0.247$


## Dataset Table

| Outlook   | Temperature | Humidity | Wind   | Play Tennis |
|-----------|-------------|----------|--------|-------------|
| Sunny     | Hot         | High     | Weak   | No          |
| Sunny     | Hot         | High     | Strong | No          |
| Overcast  | Hot         | High     | Weak   | Yes         |
| Rain      | Mild        | High     | Weak   | Yes         |
| Rain      | Cool        | Normal   | Weak   | Yes         |
| Rain      | Cool        | Normal   | Strong | No          |
| Overcast  | Cool        | Normal   | Strong | Yes         |
| Sunny     | Mild        | High     | Weak   | No          |
| Sunny     | Cool        | Normal   | Weak   | Yes         |
| Rain      | Mild        | Normal   | Weak   | Yes         |
| Sunny     | Mild        | Normal   | Strong | Yes         |
| Overcast  | Mild        | High     | Strong | Yes         |
| Overcast  | Hot         | Normal   | Weak   | Yes         |
| Rain      | Mild        | High     | Strong | No          |






