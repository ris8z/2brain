---
date: 2024-12-08 
tags: 
    - archlinux
---

# bluetooth do not work
## Controlla rfkill per blocchi

È possibile che il Bluetooth sia bloccato. Usa rfkill per verificare:
`rfkill list bluetooth` 

Se l'output mostra Soft blocked: yes o Hard blocked: yes, sblocca il dispositivo con:
`rfkill unblock bluetooth` 

Poi prova di nuovo:
`bluetoothctl power on` 


