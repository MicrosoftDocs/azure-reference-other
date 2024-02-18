---
title: Example log table queries for AGSGrafanaLoginEvents
description:  Example queries for AGSGrafanaLoginEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AGSGrafanaLoginEvents table


### Show login error events  


A list of login error event sorted by time.  

```query
AGSGrafanaLoginEvents
| where Level == "Error"
| sort by TimeGenerated asc
| take 100
```

