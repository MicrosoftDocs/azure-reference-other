---
title: Example log table queries for AmlEnvironmentEvent
description:  Example queries for AmlEnvironmentEvent log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlEnvironmentEvent table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Request the history of accessing environment  


Request the history of accessing specific environment in the specific AML workspace.  

```query
AmlEnvironmentEvent 
| where  AmlEnvironmentName =="experiment_env" and  split(_ResourceId, "/")[-1]=="amlws"
| extend  Identity=(parse_json(Identity))
| where Identity.UserName!=""
| project TimeGenerated, OperationName=split(OperationName, "/")[-1], WorkspaceName=split(_ResourceId, "/")[-1], AmlEnvironmentName,AmlEnvironmentVersion,  UserName=Identity.UserName
| limit 100
```

