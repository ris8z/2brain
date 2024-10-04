---
date: 2024-10-01 
tags: 
    - tmux
---

# copy_to_cliboard_tmux

## For wayland add this to your confing

```tmux
# Copy to system clipboard using wl-copy
bind-key -T copy-mode-vi y send -X copy-pipe-and-cancel "wl-copy"

```

## Enable mouse support and vim movemnt for copying
```tmux
set -g mouse on
set-window-option -g mode-keys vi
```

## How to use vim movement to copy?

1. Enter copy mode `prefix + [` 
2. Move with hjkl and start the slection by pressince `SPACE` 
3. Press `y` to copy

