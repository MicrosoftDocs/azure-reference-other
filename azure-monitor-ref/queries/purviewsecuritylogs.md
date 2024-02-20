---
title: Example log table queries for PurviewSecurityLogs
description:  Example queries for PurviewSecurityLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the PurviewSecurityLogs table


### Audit collection delete events  


Display audit logs for collection delete events.  

```query
PurviewSecurityLogs
| where EntityType == 'Collections'
| where OperationName == 'Delete'
| take 100
```

