---
date: 2025-03-08 
tags: 
    - nvim
---

# tab char in nvim for makefiles

## base config
by default in you config you have (that expands tab into spaces)
```vim
set expandtab
```

## how to insert a tab
you can disable this with (and now you can just type tab)
```vim
:set expandtab!
```

or use insert a tab with `ctl+v`  and then `tab` 

## how to check if there are tabs chars
to check if the whitespaces are spaces or tab char you can use 
```vim
:set list
```
and then disable it with
```vim
:set list!
```
