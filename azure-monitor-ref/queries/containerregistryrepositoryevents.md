---
title: Example log table queries for ContainerRegistryRepositoryEvents
description:  Example queries for ContainerRegistryRepositoryEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ContainerRegistryRepositoryEvents table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Show registry events reported over the last hour  


A list of registry event logs, sorted by time (earliest logs shown first).  

```query
ContainerRegistryRepositoryEvents
| where TimeGenerated > ago(1h)
| sort by TimeGenerated asc
```

