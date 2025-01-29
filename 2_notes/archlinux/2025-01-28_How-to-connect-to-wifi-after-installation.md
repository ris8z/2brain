---
date: 2025-01-28 
tags: 
    - archlinux
---

# How to connect to wifi after installation

## list all wifis
```bash
nmcli device wifi list
```
## Connect to a wifi  
```bash
nmcli device wifi connect 'NAME' password 'PASSWORD'
```



