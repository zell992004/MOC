---
id: ki547dsa23pt58hf823pto6
title: smb-setup
desc: ''
updated: 1702828253469
created: 1702828239273
---

``` bash
#!/bin/bash

# Set the required variables
share_name="myshare"
share_path="/path/to/share"
remote_host="remote_host_ip"
remote_user="remote_username"
remote_password="remote_password"
mount_point="/mnt/${share_name}"

## Create the SMB share

smbclient -U "${remote_user}%${remote_password}" -c "mkdir ${share_name}; exit" "//${remote_host}/${share_name}"

### Set the SMB password for the user

echo -e "${remote_password}\n${remote_password}" | sudo smbpasswd -s -a "${remote_user}"

#### Mount the SMB share

sudo mount -t cifs "//${remote_host}/${share_name}" "${mount_point}" -o username="${remote_user}",password="${remote_password}"

##### Optional: Automatically mount the share at boot

echo -e "//${remote_host}/${share_name}\t${mount_point}\tcifs\tusername=${remote_user},password=${remote_password}\t0\t0" | sudo tee -a /etc/fstab
```