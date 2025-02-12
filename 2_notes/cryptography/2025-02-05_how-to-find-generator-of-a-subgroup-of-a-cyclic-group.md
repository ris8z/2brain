---
date: 2025-02-05 
tags: 
    - cryptography 
hubs: 
    -   "[[2025-02-05_Pedersan-Commitments|Pedersan Commitments]]"
---

# How to find generator of a subgroup of a cyclic group

## 1. General Formula for Finding Generators of Subgroups

### **Given:**
- A **cyclic group** $G$ of order $n$ (e.g., $\mathbb{Z}_p^*$ with $p$ prime and $n = p - 1$).
- A **subgroup** $H$ of order $q$, where $q \mid n$ (i.e., $q$ divides $n$).

### **Method to Find Subgroup Generators:**
1. **Find a generator $g$ of the full group $G$.**  
   - This $g$ generates all $n$ elements of the group.

2. **Compute:**
   $$
   h = g^{\frac{n}{q}} \mod p
   $$
   - This $h$ is a **generator of the subgroup** of order $q$.

3. **Verification:**
   - Ensure that $h$ generates exactly $q$ distinct elements. If so, $h$ is a valid generator for the subgroup.

---

## 2. Practical Example: $\mathbb{Z}_{23}^*$

Let's consider the **multiplicative group modulo 23**.

### **Order of the Group $n$:**
$$
|\mathbb{Z}_{23}^*| = 23 - 1 = 22
$$

### **Choose the Order of the Subgroup $q$:**
- We choose $q = 11$ (since $11$ divides $22$).

---

## **Step 1: Find a Generator of the Full Group**
Suppose that $g = 5$ is a generator of $\mathbb{Z}_{23}^*$.

### **Verify that $g = 5$ is a Generator:**
We calculate the powers of $5$ modulo $23$:

1. $5^1 \mod 23 = 5$  
2. $5^2 \mod 23 = 25 \mod 23 = 2$  
3. $5^3 \mod 23 = 10$  
4. $5^4 \mod 23 = 50 \mod 23 = 4$  
5. $5^5 \mod 23 = 20$  
6. $5^6 \mod 23 = 8$  
7. $5^7 \mod 23 = 17$  
8. $5^8 \mod 23 = 16$  
9. $5^9 \mod 23 = 11$  
10. $5^{10} \mod 23 = 9$  
11. $5^{11} \mod 23 = 22$  
12. $5^{12} \mod 23 = 18$  
13. $5^{13} \mod 23 = 21$  
14. $5^{14} \mod 23 = 13$  
15. $5^{15} \mod 23 = 19$  
16. $5^{16} \mod 23 = 3$  
17. $5^{17} \mod 23 = 15$  
18. $5^{18} \mod 23 = 6$  
19. $5^{19} \mod 23 = 7$  
20. $5^{20} \mod 23 = 12$  
21. $5^{21} \mod 23 = 14$  
22. $5^{22} \mod 23 = 1$  

Since we obtained **all 22 elements**, $g = 5$ is a **valid generator** of $\mathbb{Z}_{23}^*$.

---

## **Step 2: Find the Generator of the Subgroup**

Now we calculate the **generator of the subgroup of order 11** using the formula:

$$
h = g^{\frac{n}{q}} \mod p
$$

Where:
- $g = 5$
- $n = 22$
- $q = 11$
- $p = 23$

Thus:
$$
h = 5^{\frac{22}{11}} \mod 23 = 5^2 \mod 23 = 25 \mod 23 = 2
$$

---

## **Step 3: Verify that $h = 2$ Generates the Subgroup**
Now we compute the powers of $2$ modulo $23$:

1. $2^1 \mod 23 = 2$  
2. $2^2 \mod 23 = 4$  
3. $2^3 \mod 23 = 8$  
4. $2^4 \mod 23 = 16$  
5. $2^5 \mod 23 = 32 \mod 23 = 9$  
6. $2^6 \mod 23 = 18$  
7. $2^7 \mod 23 = 13$  
8. $2^8 \mod 23 = 3$  
9. $2^9 \mod 23 = 6$  
10. $2^{10} \mod 23 = 12$  
11. $2^{11} \mod 23 = 1$  

### **Result:**
$$
\{1, 2, 3, 4, 6, 8, 9, 12, 13, 16, 18\}
$$

We obtained **11 distinct elements**, so $h = 2$ is a **valid generator** of the **subgroup of order 11**.

---

## 4. How to Find Other Generators of the Subgroup?

Once you have found a generator $h$ of the subgroup, you can find other generators using the following method:

1. **Other generators are powers of $h$ where the exponent is coprime with $q$.**

For example, if $q = 11$, the numbers **coprime** with 11 are:
$$
1, 2, 3, 4, 5, 6, 7, 8, 9, 10
$$

To find another generator of the subgroup, calculate:
$$
h^k \mod p \quad \text{where } \gcd(k, q) = 1
$$

---

## 5. Conclusion:

- **Formula to find a generator of the subgroup:**
  $$
  h = g^{\frac{n}{q}} \mod p
  $$
  where $g$ is a generator of the full group.

- **Verification:**
  Ensure that $h$ generates exactly $q$ distinct elements.

- **Finding other generators:**
  Use powers of $h$ that are **coprime** with $q$.


