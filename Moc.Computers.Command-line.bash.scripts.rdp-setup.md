---
id: 8muerxzbohznubfzel6jsp1
title: rdp-setup
desc: ''
updated: 1702828257985
created: 1702828211410
---

``` bash
#!/bin/bash

# Update package list
sudo apt update

# Install Xrdp
sudo apt install -y xrdp

# Add the xrdp user to the ssl-cert group
sudo adduser xrdp ssl-cert

# Configure Xrdp to use the Ubuntu session
echo "ubuntu-session" > ~/.xsession

# Restart the xrdp service
sudo service xrdp restart

# Enable the xrdp service to start on boot
sudo systemctl enable xrdp

# Allow RDP traffic through the firewall (if enabled)
sudo ufw allow 3389

echo "RDP has been enabled on the Ubuntu machine."
```