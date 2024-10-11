---
date: 2024-10-05 
tags: 
    - python
---

# append_vs_extend

## append, add to the list the its arguments as one element
```python3
a = [1,2,3]
b = [4,5]
print(a.append(b) # [1,2,3,[4,5]]
```
## extend, add to the list every element in extend, as different element
```python3
a = [1,2,3]
b = [4,5]
print(a.extend(b) # [1,2,3,4,5]
```


