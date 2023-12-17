---
id: d69pyrg33v23r6vjn4gh4vg
title: one-liners
desc: ''
updated: 1702841370000
created: 1702827494846
---


[Month of PowerShell - Offensive PowerShell with Metasploit Meterpreter | SANS Institute](https://www.sans.org/blog/offensive-powershell-metasploit-meterpreter/)
Great resource of non auto exploit PowerShell stuffs

``` powershell
Get-Content "C:\path\to\targets.txt" | ForEach-Object { if (Test-Connection -ComputerName $_ -Count 1 -Quiet) { Write-Host "$_ is reachable." } else { Write-Host "$_ is unreachable." } }

```

```powershell 
Get-Command <cmdlet>
```

```powershell
Invoke-WebRequest -Uri '<url/item2dl>' -OutFile <path/to/save/to.extension>
```
``` powershell
iwr -uri "url" -outfile "url"
```

``` powershell
Get-CimInstance Win32_ComputerSystemProduct | Select-Object -ExpandProperty UUID
```