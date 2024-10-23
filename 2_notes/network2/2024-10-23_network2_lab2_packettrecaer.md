---
date: 2024-10-23 
tags: 
    - network2
hubs:
    - [[2024-10-23_network2_lab2|network2_lab2]]
---

# Network2_lab2_packettrecaer

## Use a console connection to access each switch

1. take the blu skye calbe called **console**
2. Student-1 (**RS 232**) --> (**console**) Class-A
3. Student-2 (**RS 232**) --> (**console**) Class-B

## Name Class-A and Class-B switches

use the terminal (open pc, go desktop, go terminal, click ok)

1. Open the terminal in Student-1 and type:
```bash
enable
configure terminal
hostname Class-A
```
2. Open the terminal in Student-2 and type:
```bash
enable
configure terminal
hostname Class-B
```

## Use the xAw6k password for all lines

for each console (Student-1 and Student-2) open the terminal and the type:
```bash
enable
configure terminal
line console 0
password xAw6k
login
exit
```
DO NOT COLSE the terminal and follow the info:

## Use the 6EBUp secret password

for each terminal (Student-1 and Student-2) type:
```bash
enable secret 6EBUp
```

## Encrypt clear text password

for each terminal (Student-1 and Student-2) type:
```bash
service password-encryption
```

## Configuire a MOTD banner

for each terminal (Student-1 and Student-2) type:

```bash
banner motd "Welcome to the network, Unauthorized access is not permitted"
```

## Configure addressing for all devices according to the Addressing 

1. For switch 1 (Class-A) (choose the right ip from the table)
```bash
interface vlan 1
ip address 10.10.10.100 255.255.255.0
no shutdown
exit
```
2. For switch 2 (Class-A)
```bash
interface vlan 1
ip address 10.10.10.150 255.255.255.0
no shutdown
exit
```

## Save configuration

for each terminal (Student-1 and Student-2) type:

first type ctrl-z to exit the config state

```bash
copy running-config startup-config
```

## Configure PCs with IP addresses
for student 1 and 2
- open the pc, than desktop tab, then **IP Configuration**
- use (IPV4)
- put the right ip addresses form the tablbe
- put also the right subnet from the table 

## Test if the network is working
- open student 1 go to desktop then prompt
- than ping the addres of the student 2 pc
- if it works good if not (Ohhh noooo)

