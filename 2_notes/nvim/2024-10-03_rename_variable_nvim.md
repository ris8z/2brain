---
date: 2024-10-03 
tags: 
    - nvim
---

# rename_variable_nvim

## base pattern is
`s/old_var/new_var/g` 

## Different range

`:s/old_var/new_var/g` *nothing* before s means the *current line*
`:%s/old_var/new_var/g` *%* before means the *whole file*
`:'<,'>s/old_var/new_var/g`  *'<,'>* before s means the *selected area*

> [!TIP]
> the '<,'> is going to be automatically added if u select your are first

> [!WARNING]
> without /g is going to rename just the first occurence
of the old var with the new var for each line selected


