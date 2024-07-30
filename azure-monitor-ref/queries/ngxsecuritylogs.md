---
title: Example log table queries for NGXSecurityLogs
description:  Example queries for NGXSecurityLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the NGXSecurityLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Show NGINXaaS security logs  


A list of security logs sorted by time.  

```query
NGXSecurityLogs
| where FilePath == "/var/log/nginx/security.log"
| sort by TimeGenerated asc
| take 100
```

