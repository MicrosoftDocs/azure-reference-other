---
title: Example log table queries for ASRJobs
description:  Example queries for ASRJobs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ASRJobs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Get all test failover jobs run  


Get all test failover jobs run for your ASR protected items to verify if recoverability is being tested regularly for all your important resources.  

```query
ASRJobs
//| where TimeGenerated >= ago(30d) // uncomment this line to view last 30 days
| summarize arg_max(TimeGenerated,*) by JobUniqueId
| where OperationName == "Test failover"
| project StartTime, EndTime, SourceResourceId, SourceFriendlyName, DurationMs, ResultDescription
```

