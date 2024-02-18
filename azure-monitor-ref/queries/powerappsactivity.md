---
title: Example log table queries for PowerAppsActivity
description:  Example queries for PowerAppsActivity log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the PowerAppsActivity table


### Power Apps events filtered activity type  


Display events from more than one day ago, filtered by app launch activity events and summarized by user ID, app and environment.  

```query
PowerAppsActivity
| where EventOriginalType == "LaunchPowerApp"
| extend Environment = tostring(AdditionalData.environmentName)
| summarize count() by ActorName, TargetAppName, Environment
```

