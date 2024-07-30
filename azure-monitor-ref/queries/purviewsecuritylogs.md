---
title: Example log table queries for PurviewSecurityLogs
description:  Example queries for PurviewSecurityLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the PurviewSecurityLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Audit collection delete events  


Display audit logs for collection delete events.  

```query
PurviewSecurityLogs
| where EntityType == 'Collections'
| where OperationName == 'Delete'
| take 100
```

