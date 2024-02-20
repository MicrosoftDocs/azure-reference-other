---
title: Example log table queries for DeviceHealth
description:  Example queries for DeviceHealth log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DeviceHealth table


### Software Alert  


SurfaceHub software error.  

```query
DeviceHealth
| where EventName == "CriticalProcessStatus" and State == "Unhealthy" 
| sort by TimeGenerated desc
```

