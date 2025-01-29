---
date: 2025-01-26 
tags: 
    - git
hubs: 
    -   "[[2025-01-26_git-basics|git basics]]"
---

# git ignore file

## How to use it?

### Create a .gitignore file in the parent folder
```bash
touch .gitignore
```

### Add rules to the gitignore file
```bash
# Ignore virtual environments in any folder
**/env/
**/venv/

# Ignore Python bytecode cache directories in any folder
**/__pycache__/

# Optionally ignore all compiled Python files (.pyc) in any folder
**/*.pyc
```
## How to remove already traked files?

### remove the file from the track for all dirs and sub dirs
```bash
git rm -r --cached **/env **/venv **/__pycache__
```
### add the .gitignore
```bash
git add .gitignore
```
### create a commit with a massage
```bash
git commit -m "Ignore env, venv, and __pycache__ folders across all directories"
```
