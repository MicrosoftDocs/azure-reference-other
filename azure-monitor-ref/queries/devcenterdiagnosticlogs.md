---
title: Example log table queries for DevCenterDiagnosticLogs
description:  Example queries for DevCenterDiagnosticLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DevCenterDiagnosticLogs table


### Failed actions query  


Summarizes the number and type of operations that have failed.  

```query
DevCenterDiagnosticLogs
| where toint(ResponseCode) >= 400 
| extend _date = bin(TimeGenerated, 1d)
| summarize failureCount = count() by OperationName, _date
| sort by _date desc
```

