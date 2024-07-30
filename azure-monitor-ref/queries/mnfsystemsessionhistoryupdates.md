---
title: Example log table queries for MNFSystemSessionHistoryUpdates
description:  Example queries for MNFSystemSessionHistoryUpdates log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the MNFSystemSessionHistoryUpdates table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Find all entries where session update user is admin  


System session history update events are projected from devices. This query will list out all logs where session update user is admin.  

```query
MNFSystemSessionHistoryUpdates
| where EventCategory == "SystemSessionHistoryUpdates"
| project EventName, EventCategory, DeviceId, DeviceName, FabricId, TimeGenerated, DiffTimeStamp, GnmiTimeStamp, SessionUpdateSessionId, SessionUpdateUser, SessionDiffs
| sort by TimeGenerated desc
| limit 100
```

