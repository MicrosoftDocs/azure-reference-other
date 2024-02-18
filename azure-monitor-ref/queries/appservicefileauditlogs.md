---
title: Example log table queries for AppServiceFileAuditLogs
description:  Example queries for AppServiceFileAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AppServiceFileAuditLogs table


### File Audit Logs relating to a "Delete" operation  


List File Audit Logs that has a "Delete" operation.  

```query
// To create an alert for this query, click '+ New alert rule'
AppServiceFileAuditLogs
| where OperationName == "Delete"
```

