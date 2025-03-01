---
date: 2025-03-01 
tags: 
    - archlinux
hubs: 
    -   "[[]]"
---

# change shell to zsh

## start setup
### install it
```bash
sudo pacman -S zsh
```
### change shell
```bash
chsh -s $(which zsh)
```

### create a config file
```bash
touch ~/.zshrc
```
## configure ~/.zshrc

### (zinit) add these lines to the file
```bash
# Created by newuser for 5.9

# set the directory we want to install zinit and plugins
ZINIT_HOME="${XDG_DATA_HOME:-${HOME}/.local/share}/zinit/zinit.git"

# download zinit if the zinit folder do not exist
if [ ! -d "${ZINIT_HOME}" ]; then
    mkdir -p "$(dirname $ZINIT_HOME)"
    git clone https://github.com/zdharma-continuum/zinit.git "$ZINIT_HOME"
fi

# source our zinit file
source "${ZINIT_HOME}/zinit.zsh"
```

### check with
```bash
source ~/.zshrc
zinit status
```

### powerlevel10k (propmpt style like starship)
add to the file
```bash
zinit ice depth=1; zinit light romkatv/powerlevel10k
```
then source the file and do the setup

### syntax-highlighting
```bash
zinit light zsh-users/zsh-syntax-highlighting
```

### completions
```bash
zinit light zsh-users/zsh-completions

# load completions
autoload -U compinit && compinit
```
### auto-suggestion
```bash
# plugins
zinit light zsh-users/zsh-autosuggestions
# keybinds
bindkey -e
```
- `cnt + f` autocomplete the suggestion / go forward on the line
- `cnt + b` go back on the line 
- `cnt + a` jump to start of line 
- `cnt + e` jump to end of line 
- `cnt + p` previous command used 
- `cnt + n` next command used 

### History and keybinds settings 
```bash
# Keybinds
bindkey -e
bindkey '^p' history-search-backward # se inzi a scrive tipo curl ti da  vecchi comandi che startano con quello
bindkey '^n' history-search-forward

# History
HISTSIZE=50000
HISTFILE=~/.zsh_history
SAVEHIST=$HISTSIZE
HISTDUP=erase
setopt appendhistory
setopt sharehistory
setopt hist_ignore_space
setopt hist_ignore_all_dups
setopt hist_save_no_dups
setopt hist_ignore_dups
setopt hist_find_no_dups
```

