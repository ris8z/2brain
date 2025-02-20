---
date: 2025-02-19 
tags: 
    - archlinux
urls:
    - https://itsfoss.com/install-docker-arch-linux/
---

# install docker on arch linux

## Install Docker

install docker
```bash
sudo pacman -S docker
```

start the docker deamon
```bash
sudo systemctl start docker.service
```

enable the automatic starting of the docker deamon when you boot your machine
```bash
sudo systemctl enable docker.service
```

To avoid using sudo with each docker command, you can add yourself (or any other user) to the docker group like this:
```bash
sudo usermod -aG docker $USER
```
You must log out (or close the terminal) and log back in for the above change to take effect. If you don't want to do that, use this command:
```bash
newgrp docker
```
Verify you docker installation with
```bash
docker run hello-world
```

## Install Docker compose
install docker-compose (python package)
```bash
sudo pacman -S docker-compose
```
