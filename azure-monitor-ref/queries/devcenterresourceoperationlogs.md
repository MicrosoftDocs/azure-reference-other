---
title: Example log table queries for DevCenterResourceOperationLogs
description:  Example queries for DevCenterResourceOperationLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DevCenterResourceOperationLogs table


### Hibernate Unsupported Check  


Returns the number of occurences of each type of inegibility check for hibernate on dev boxes.  

```query
DevCenterResourceLifecycleLogs
| where OperationName == "HibernateSupportStatusCheck"
| extend Date = bin(TimeGenerated, 6h)
| summarize unsupportedCount = count() by Message, Date
| sort by Date desc
```

