---
id: vib4prxzorjl9p7j4eijouk
title: ssh-setup
desc: ''
updated: 1702828295744
created: 1702828280973
---

``` bash
#!/bin/bash

# For current user


# Install SSH server
sudo apt update
sudo apt install -y openssh-server

# Configure SSH server
sudo sed -i 's/#Port 22/Port 22/' /etc/ssh/sshd_config
sudo sed -i 's/PermitRootLogin yes/PermitRootLogin no/' /etc/ssh/sshd_config
sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config
sudo sed -i 's/#PubkeyAuthentication yes/PubkeyAuthentication yes/' /etc/ssh/sshd_config

# Restart SSH service
sudo service ssh restart

# Configure firewall
sudo ufw allow 22
sudo ufw enable

echo "SSH configuration completed successfully."
```