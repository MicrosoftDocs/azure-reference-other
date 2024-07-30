---
title: Example log table queries for SecurityAttackPathData
description:  Example queries for SecurityAttackPathData log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the SecurityAttackPathData table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### All attack paths by specific risk level  


Get all attack paths with a specific risk level such as: Critical, High, Medium, and Low.  

```query
SecurityAttackPathData
| where RiskLevel == "Medium"
| limit 100
```

