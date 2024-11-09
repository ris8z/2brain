---
date: 2024-11-09 
tags: 
    - #archlinux
---

# change_cursors_hyprland

Install your cursors theme i like this one:

```bash
yay -S catppuccin-cursors-mocha
```

Then serach for the full name with

```bash
ls -d /usr/share/icons/* ~/.icons/*
```

You can even filter by cursor keyword
```bash
ls -d /usr/share/icons/*cursors* ~/.icons/*cursors*
```

Then u can apply the theme to your hyprland with in your terminal

```bash
hyprctl setcursor catppuccin-mocha-dark-cursors 24
```

And for make it work also on gtk application install **gnome tweaks** and select
the same theme.

> [!TIP]
> Add exec-once=hyprctl setcursor [THEME] [SIZE] to your config and restart Hyprland.


> [!TIP]
> you also want to add (bc gnome tweaks rest it every time idk why)
exec-one=gsettings set org.gnome.desktop.interface cursor-theme "catppuccin-mocha-dark-cursors"

