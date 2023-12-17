---
id: v9kxl7ncwslmxjovoys1z88
title: system-processes
desc: ''
updated: 1702841396130
created: 1702841390343
---


#enumeration #processes #windows #powershell #bash

```powershell
schtasks /query /fo LIST /v
```

```bash
cat schtask.txt | grep "SYSTEM\|Task To Run" | grep -B 1 SYSTEM
```