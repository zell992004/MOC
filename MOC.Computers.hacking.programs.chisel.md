---
id: upya79hdpst0g882yrg4pki
title: chisel
desc: ''
updated: 1702841239775
created: 1702840810199
---

#proxy #tunneling

on server

./chisel server -p 8080 --reverse

|Command   |Notes    |
|---|---|
|`chisel client 10.10.14.3:8000 R:80:127.0.0.1:80`|Listen on Kali 80, forward to localhost port 80 on client|
|`chisel client 10.10.14.3:8000 R:4444:10.10.10.240:80`|Listen on Kali 4444, forward to 10.10.10.240 port 80|
|`chisel client 10.10.14.3:8000 R:socks`|Create SOCKS5 listener on 1080 on Kali, proxy through client|

#Proxychains

add this to /etc/proxychains4.conf

socks5 127.0.0.1 1080

Iterate as x080