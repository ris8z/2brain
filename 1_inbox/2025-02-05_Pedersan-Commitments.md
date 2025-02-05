---
date: 2025-02-05 
tags: 
    - cryptography
url:
    - https://www.zkdocs.com/docs/zkdocs/commitments/pedersen/
---

# Pedersan Commitments
## Math definition

### Z number set
is the set of number with N + 0 + negative numbers
#### Example
... -2, -1, 0, 1, 2, ...

### Group
A *set* with an *operation* that can ensure these 4 points is a Group

- Closure 
  - (after the *operation* between two element of the set the result must be in the set)
- Identity Element 
  - (there is an element in the set that does not change other elements when used in the *operation*)
  - (i.e. $0$ for addition, $1$ for moltiplication)
- Inverse
  - (Every element has an opposite that brings back to the Identity Element, when combined with the *operation*)
  - ($a + ( -a) = 0$)
- Associativity
  - (The grouping of the operation doesn't affect the result)
  - ($(a*b)*c=a*(b*c)$)

#### Example Z3 Mod3 Set
$(Z_3, + )$ 
$Z_3 = \{0,1,2\}$

- Closure 
  - $(0 + 1) \bmod 3 = 1$
  - $(0 + 2) \bmod 3 = 2$
  - $(0 + 3) \bmod 3 = 3$
  - ... 
- Identity 
  - $(2 + 0) \bmod 3 = 2$
- Inverse 
  - $(0 + 0) \bmod 3 = 0$
  - $(1 + 2) \bmod 3 = 0$
  - $(2 + 1) \bmod 3 = 0$
- Associativity
  - $(a+b)+c \bmod 3 = a+(b+c) \bmod 3$

### Group Order
Just how many elements are in the group

### SubGroup
Just a subset of the group that still holds the 4 points (Closure,Identity,Inverse,Associativity)

### Generator
A generator of a group is an *element* that using the group operation (on itslef) *can generate all* the other ones
- i.e. ($1$ for the example Z3 Mod3)
  - $(1 + 1 + 1) \bmod 3 = 0$
  - $(1 + 1) \bmod 3 = 2$
  - $(1) \bmod 3 = 1$

One just one element of a group can generate all the other ones the group is calld *cyclic*

[[2025-02-05_how-to-find-generator-of-a-subgroup-of-a-cyclic-group|how to find generator of a subgroup of a cyclic group]]

### Lagrange's Theoream
**In a finite group, the order of any sub-groups must divide the order of the group**
#### Example: Subgroups of $\mathbb{Z}_7^*$

Let's consider the **multiplicative group modulo 7**:

##### Definition of the Group:
$$
\mathbb{Z}_7^* = \{1, 2, 3, 4, 5, 6\}
$$
This group operates under **multiplication modulo 7**.

##### Order of the Group:
$$
|G| = 6
$$
There are 6 elements in the group.

##### Possible Orders of Subgroups:
According to **Lagrange's Theorem**, the order of any subgroup must **divide the order of the group**.

The divisors of 6 are:
$$
1, 2, 3, 6
$$

So, the subgroups can have **1**, **2**, **3**, or **6** elements.

---

##### Verification of Subgroups:

###### **Subgroup of Order 1:**
This is the **trivial subgroup** that contains only the identity element:
$$
\{1\}
$$

---

###### **Subgroup of Order 2:**
We need to find an element that, when squared, gives 1 modulo 7.

**Verification with 6:**
$$
6^2 \mod 7 = 36 \mod 7 = 1
$$

Thus:
$$
\{1, 6\}
$$
is a **subgroup of order 2**.

---

###### **Subgroup of Order 3:**
We need to find an element that generates 3 distinct elements.

**Verification with 2:**
$$
2^1 \mod 7 = 2
$$
$$
2^2 \mod 7 = 4
$$
$$
2^3 \mod 7 = 8 \mod 7 = 1
$$

Thus:
$$
\{1, 2, 4\}
$$
is a **subgroup of order 3**.

---

###### **Subgroup of Order 6:**
This is the entire group itself:
$$
\{1, 2, 3, 4, 5, 6\}
$$

---

## Formal definition

### It is a tuple $(G,q,g,h)$

- *G*
  - It is a *finite group* of order q, where *q* is suitably large.
  - (i.e. a subgroup of $(Z_p, *)$ with order $q$ where $q$ divides $p - 1$)
- *q*
  - It is the *order* of the group *G*
- *g* and *h*
  - g and h are two *generators* of G such that $\log_{g}\left(h\right)$


# add notes on $(Z_p, *)$, and why it's better to take a subset
## note that

### *Lato Client:*
Generi il commitment:
$$
c = g^s \cdot h^t \mod p
$$
e invii **$s$** e **$t$** al server quando vuoi "aprire" il commitment.

---

### *Lato Server:*
Usa **$s$** e **$t$** per verificare che il commitment corrisponda al valore ricevuto:
$$
c' = g^s \cdot h^t \mod p
$$
Se **$c' = c$**, il commitment è valido.

---

### *Generatori $g$ e $h$:*
I generatori **$g$** e **$h$** devono essere **noti a entrambe le parti**.  
- Se **non sono pubblici**, devi includerli nella comunicazione.
