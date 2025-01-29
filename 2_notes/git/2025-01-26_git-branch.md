---
date: 2025-01-26 
tags: 
    - git
hubs: 
    -   "[[2025-01-26_git-basics|git basics]]"
---

# git branch

## Branch commands

### 1) List branches
#### List local branches
```bash
git branch
```

#### List remote branches
```bash
git branch -r
```

#### List local and remote branches
```bash
git branch -a
```

### 2) Copy a remote branch as a local one

#### List all remote branchs
```bash
git branch -r
```

#### Copy the branch with the name: name_origin as a local branch named name_local
```bash
git checkout -b name_local_ name_origin 
```
#### example
```bash
git checkout -b dev origin/dev
```

### 3) Create a new branch from the one you are currently on

#### create it with:
```bash
git branch new-branch-name
```

#### swith to it with:
```bash
git checkout new-branch-name
```

#### or you can combine both actions with
```bash
git switch -c new-branch-name
```

#### **When you need to push** and so save your local branch in a new remote branch
```bash
git push -u origin new-branch-name
```
- if the branch `new-branch-name` does not exist git just create it
- `-u` means `--set-upstream` link your local branch to the remote branch named `new-branch-name`
  - in this way next time you can just use
  - `git push`
  - `git pull`
