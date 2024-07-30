---
title: Example log table queries for AWSGuardDuty
description:  Example queries for AWSGuardDuty log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AWSGuardDuty table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### High severity findings  


Returns high severity findings summarize by activity type.  

```query
AWSGuardDuty
| where Severity > 7
| summarize count() by ActivityType
```

