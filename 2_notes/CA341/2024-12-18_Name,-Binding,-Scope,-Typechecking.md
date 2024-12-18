---
date: 2024-12-18 
tags: 
    - CA341
hubs: 
    -   "[[2024-12-18_Comparative-Programming|Comparative Programming]]"
---

# Name, Binding, Scope, Type Checking
 
## Common Naming Conventions:
*camelCase*: myVariableName
*snake_case*: my_variable_name
*PascalCase*: MyVariableName

## Binding

It is an *association* between a *name* (variable, function, etc.) and an *entity* (value, object, code).
```c
int x = 10; //(C): x is bound to the value 10.
```

It can happen at:
1. *complie time* (i.e. var in c, static biding)
2. *load time* (i.e. global vars)
3. *run time* (i.e. vars in python and js, dynamic biding)

| Aspect              | Static Binding          | Dynamic Binding        |
|---------------------|-------------------------|-------------------------|
| When it occurs      | Compile-time            | Runtime                 |
| Flexibility         | Low                     | High                    |
| Error Detection     | Compile-time            | Runtime                 |
| Efficiency          | High                    | Lower                   |
| Languages           | C, Pascal, Haskell      | Python, JavaScript      |

## Scope
It is the *region of a program* where a *var* is *defined* and *can be accessed*.
- types:
  - *Local Scope* (declared within a block, access only there)
  - *Global Scope* (declared outside, access every where)
  - *Non-local Scope* (neither local or global but to find in an outer function)
  - *Built-in Scope* (keywords)

## Type Checking
It *ensures* that *operations* in a program *are performed on compatible data types*

**Difference based on when**
- *Static* 
  - Types are checked before execution.
  - Errors are caught at compile-time.
  - Examples: C, C++, Java, Haskell.
  - *safe, verbose, not flexible*
- *Dynamic* 
  - Types are checked during execution.
  - Errors occur at runtime.
  - Examples: Python, Prolog.
  - More flexible but potentially less safe.
  - *less safe, less verbose, more flexible*

**Difference based on rules**
- *Strongly* 
  - Enforce strict type rules
  - Do not allow implicit type conversion that can lead to unexpected results.
  - Examples: Python, Java, Haskell.
- *Weakly* 
  - Allow more flexibility in type conversions, often implicitly converting types as needed.
  - Can lead to more concise code, but also to bugs. 
  - Examples: C, JavaScript, Perl.

