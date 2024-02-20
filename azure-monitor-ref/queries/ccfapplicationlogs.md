---
title: Example log table queries for CCFApplicationLogs
description:  Example queries for CCFApplicationLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the CCFApplicationLogs table


### CCF application errors  


View the latest Confidential Consortium Framework application errors.  

```query
// To create an alert for this query, click '+ New alert rule'
CCFApplicationLogs
| where Level == "fail"
| sort by TimeGenerated desc
| limit 100
```

