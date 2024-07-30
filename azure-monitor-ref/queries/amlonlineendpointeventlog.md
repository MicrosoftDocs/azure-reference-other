---
title: Example log table queries for AmlOnlineEndpointEventLog
description:  Example queries for AmlOnlineEndpointEventLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlOnlineEndpointEventLog table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Online endpoint failure events  


Get the latest Azure ML online endpoints failures.  

```query
AmlOnlineEndpointEventLog
| where Message contains "failed"
| parse kind=regex flags=i _ResourceId with ".*?/RESOURCEGROUPS/" ResourceGroup "/PROVIDERS/MICROSOFT.MACHINELEARNINGSERVICES/WORKSPACES/" Workspace "/ONLINEENDPOINTS/" EndpointName
| project
    TimeGenerated,
    Subscription = _SubscriptionId,
    ResourceGroup,
    Workspace,
    EndpointName,
    DeploymentName,
    InstanceId,
    Name,
    Message
| order by TimeGenerated desc
| take 100
```

