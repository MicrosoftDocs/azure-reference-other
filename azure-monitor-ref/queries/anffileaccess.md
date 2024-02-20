---
title: Example log table queries for ANFFileAccess
description:  Example queries for ANFFileAccess log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ANFFileAccess table


### Deleted objects for an ANF volume  


Display all deleted object events for an ANF volume.  

```query
ANFFileAccess
| where OperationName == "Unlink Object"
| limit 100
```



### All Logs for a Particular Object  


Display all audit events for a particular object on an ANF volume.  

```query
ANFFileAccess
| where ObjectName == "/auditlog.txt"
| sort by TimeGenerated desc
| limit 100
```

