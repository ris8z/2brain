---
date: 2024-10-01 
tags: 
    - nvim
---

# nvim_how_to_copy_and_paste

## Context:

In nvim, every yank delete or change operation stores text in a register.


## Special registers:

The default register of nvim is `""` called the unnamed register
The system register is `"+`
The mousewheel one in linux only is `"*` 


## Named registers:

They go from a - z, where `"a` - `"z` 


## How to use it (with default register):

### Copying
To copy to the default register of nvim, just yank with `v`  (to enter visual mode)
and then press y
Or just do an action like 'yy' (copy current line) or 'dd' (delete and copy current line)

### Paste
just press p

> [!TIP]
> you can change the default register of nvim to be the system's one `+` 
in this way when u yank and copy it gets copied also to the clipboard
add this to your init.lua
```lua
vim.opt.clipboard = "unnamedplus"
```

## How to use it (with a named or special register):

### Copying

first u yank what u want to copy, then press `"ay` to copy into the a register for example

### Paste
press `"ap` and u are good to go

