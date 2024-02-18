---
title: Example log table queries for AmlOnlineEndpointConsoleLog
description:  Example queries for AmlOnlineEndpointConsoleLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlOnlineEndpointConsoleLog table


### Online endpoint console logs  


Get latest 100 online endpoint console log records.  

```query
AmlOnlineEndpointConsoleLog
| parse kind=regex flags=i _ResourceId with ".*?/RESOURCEGROUPS/" ResourceGroup "/PROVIDERS/MICROSOFT.MACHINELEARNINGSERVICES/WORKSPACES/" Workspace "/ONLINEENDPOINTS/" EndpointName
| project
    TimeGenerated,
    Subscription = _SubscriptionId,
    ResourceGroup,
    Workspace,
    EndpointName,
    DeploymentName,
    InstanceId,
    ContainerName,
    ContainerImageName,
    Message
| top 100 by TimeGenerated
```

