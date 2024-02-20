---
title: Example log table queries for DeviceSkypeHeartbeat
description:  Example queries for DeviceSkypeHeartbeat log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DeviceSkypeHeartbeat table


### Skype Error  


SurfaceHub Skype error.  

```query
DeviceSkypeHeartbeat
| where State == "Unhealthy" 
| sort by TimeGenerated desc
```

