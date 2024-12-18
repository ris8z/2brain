---
date: 2024-12-18 
tags: 
    - CA341
hubs: 
    -   "[[2024-12-18_Comparative-Programming|Comparative Programming]]"
---

# Assertions

They are *boolean expressions* that *verify* program *assumptions at runtime*.

- **How?**
  - if *ture* then program *coninues execution*
  - if *false* then program *raise an error and may halt*


- **Advantages**
  - Bug Detection
  - Code Clarity
  - Lightweight
- **Disadvantages**
  - Not for Error Handling
  - Performance Overhead
  - Disabling Assertions
- **Code Examples**
  - ```java
    //java assert expression : string;
    public class BankAccount {
        private int balance;
        public BankAccount(int initialBalance) {
            assert initialBalance >= 0 : "Balance negative";
            this.balance = initialBalance;
        }
        public void deposit(int amount) {
            assert amount > 0 : "Deposit not positive";
            balance += amount;
        }
    }
    ```
  - ```c
    // c assert(expression && string);
    #include <assert.h>
    #include <stdio.h>
    void deposit(int *balance, int amount) {
        assert(amount > 0 && "Deposit must be positive");
        *balance += amount;
    }
    int main() {
        int balance = 100;
        deposit(&balance, 50);
        deposit(&balance, -20); // Assertion fails here
        return 0;
    }
    ```
  - ```python
    #python assert expression, string
    class BankAccount:
        def __init__(self, balance):
            assert balance >= 0, "Balance is negative"
            self.balance = balance
        def deposit(self, amount):
            assert amount > 0, "Deposit is not positive"
            self.balance += amount
    ```
