---
title: Example log table queries for ASRJobs
description:  Example queries for ASRJobs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ASRJobs table


### Get all test failover jobs run  


Get all test failover jobs run for your ASR protected items to verify if recoverability is being tested regularly for all your important resources.  

```query
ASRJobs
//| where TimeGenerated >= ago(30d) // uncomment this line to view last 30 days
| summarize arg_max(TimeGenerated,*) by JobUniqueId
| where OperationName == "Test failover"
| project StartTime, EndTime, SourceResourceId, SourceFriendlyName, DurationMs, ResultDescription
```

