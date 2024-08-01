---
title: Example log table queries for AgriFoodApplicationAuditLogs
description:  Example queries for AgriFoodApplicationAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AgriFoodApplicationAuditLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Failed authorization  


Identifies a list of users who failed to access your resource and the reason for this failure.  

```query
AgriFoodApplicationAuditLogs
| where OperationName startswith "Data Plane Authentication"
| where ResultType == "Failure"
| take 100

```

