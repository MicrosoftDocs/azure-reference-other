---
title: Example log table queries for AppServiceAuditLogs
description:  Example queries for AppServiceAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AppServiceAuditLogs table


### Audit Logs relating to unexpected users  


List Audit Logs for users who logged in that aren't a listed user.  

```query
// To create an alert for this query, click '+ New alert rule'
AppServiceAuditLogs
| where UserDisplayName != "user@company.com"
```

