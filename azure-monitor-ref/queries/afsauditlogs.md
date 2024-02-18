---
title: Example log table queries for AFSAuditLogs
description:  Example queries for AFSAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AFSAuditLogs table


### Aggregate operations query  


List all the UnsuspendAmlFilesystem requests for a givein time duration.  

```query
AFSAuditLogs
// The OperationName below can be replaced by obtain other operations such as "RebootAmlFilesystemNode" or "AmlFSRefreshHSMToken".
| where OperationName has "UnsuspendAmlFilesystem"
| project TimeGenerated, _ResourceId, ActivityId, ResultSignature, ResultDescription, Location
| sort by TimeGenerated asc
| limit 100

```



### Unauthorized requests query  


Count of failed AMLFilesystems requests due to unathorized access.  

```query
AFSAuditLogs
// 401 below could be replaced by other result signatures to obtain different operation results.
// For example, 'ResultSignature == 202' to obtain accepted requests.
| where ResultSignature == 401
| summarize count() by _ResourceId, OperationName
```

