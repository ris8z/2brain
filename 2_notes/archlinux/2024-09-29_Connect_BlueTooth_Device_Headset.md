---
date: 2024-09-29 
tags: 
    - archlinux
---

# Connect_BlueTooth_Device_Headset

> [!CAUTION]
> This guide is for pulseaudio, requirements:
`sudo pacman -S bluez bluez-utils pulseaudio-bluetooth pavucontrol`

## Enable and start the Bluetooth service
    `sudo systemctl enable bluetooth` 
    `sudo systemctl start bluetooth` 

## Check if the Bluetooth service is active 
    `rfkill list` 
    If the bluetooth service is blocked: `rfkill unblock bluetooth` 

## Connect to the headset by using bluetoothctl
    ENABLE AGENT FOR PAIRING:
    `bluetoothctl` 
    `agent on` 
    `default-agent` 

    ENABLE BLUETOOTH AND SEARCH FOR DEVICES
    `power on` 
    `scan on` 

    PAIR AND CONNECT TO THE HEADSET:
    `pair XX:XX:XX:XX:XX:XX` 
    `connect XX:XX:XX:XX:XX:XX` 

    ADD THE DEVICE TO THE TRUSTED ONES (OPTIONAL)
    `trust XX:XX:XX:XX:XX:XX` 
    `scan off` 
    `exit` 

## Change output audi with pavucontrol
    use the gui with: `pavucontrol` 

## Test
    `speaker-test` 

## Re-connecting to a trusted device:
    `sudo systemctl start bluetooth` 
    `bluetoothctl connect XX:XX:XX:XX:XX:XX`  

> [!TIP]
> to get the mac-address: `bluetootctl devices` 

## Write a simple script like this one to connect
```bash
#!/bin/bash
# Start Bluetooth service if not running
sudo systemctl start bluetooth

# Wait a few seconds to ensure the service is fully started
sleep 2

# Connect to the Bluetooth device (replace XX:XX:XX:XX:XX:XX with your device's MAC address)
bluetoothctl connect XX:XX:XX:XX:XX:XX
```
