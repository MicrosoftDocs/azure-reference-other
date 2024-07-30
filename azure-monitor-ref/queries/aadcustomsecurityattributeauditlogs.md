---
title: Example log table queries for AADCustomSecurityAttributeAuditLogs
description:  Example queries for AADCustomSecurityAttributeAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADCustomSecurityAttributeAuditLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### User's custom security attribute audits  


Returns custom security attribute audit logs for a specific user.  

```query
AADCustomSecurityAttributeAuditLogs
| extend targetUPN = parse_json(TargetResources)[0].userPrincipalName
| where targetUPN == 'CSALogTester@tenant.com'
| limit 100
```

