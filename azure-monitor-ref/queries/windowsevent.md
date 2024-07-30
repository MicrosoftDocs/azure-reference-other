---
title: Example log table queries for WindowsEvent
description:  Example queries for WindowsEvent log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the WindowsEvent table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### WindowsEvent Audit Policy Events  


Display events where audits were cleared (EventId = 1102) or changed (EventId = 4719).  

```query
WindowsEvent
| where Provider == 'Microsoft-Windows-Security-Auditing' 
| where EventID == 1102 or EventID == 4719
| extend DescriptionMessage = iff(EventID == 1102, 'Audit log was cleared', 'System audit policy was changed')
| take 100
```

