---
date: 2024-09-28
tags:
  - nvim
---


# nvim_buffers_windows_tabs

## Buffers
    WHAT?
    are file loaded into memory (you can see the buffer as the file itself)

    COMMAND: 
    - list buffer `:ls` 
    - open buffer `:b <buffer name>` *filename*  
    - open buffer `:b <buffer number>`  
    - next buffer `:bn`  
    - previus buffer `:bp`  
    - close buffer `:bd`  
    

> [!TIP]
> you can load more than one file as buffer while u open nvim
`nvim file1.txt file2.txt file3.txt`

    
----------

## Windows
    WHAT?
    are literally windows where u can use to see the conent of a buffer

    COMMAND:
    - horizontal split `:sp <filename>`  
    - vertical split `:vsp <filename>`  
    - move ctrl + w + (hjkl)    (normalmode)
    - close `:q`  
    
> [!TIP]
> you can have 2 windows linked to the same file, so you can edit different part at the same time

----------

## Tabs
    WAHT?
    are collections of windows

    COMMAND:
    - open empty `:tabnew` 
    - open `tabnew <filename>` 
    - next tab g+t      (normalmode)
    - previus tab g+T   (normalmode)
    - close `:tabclose` 
    - close `:tabclose <number>` 
    - close all except the current `:tabonly` 

> [!TIP]
> you can open more than one file (load as buffers into memory) each one in a separated tab 
`nvim -p file1.txt file2.txt file3.txt` 

----------
    
