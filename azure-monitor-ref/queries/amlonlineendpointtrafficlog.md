---
title: Example log table queries for AmlOnlineEndpointTrafficLog
description:  Example queries for AmlOnlineEndpointTrafficLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlOnlineEndpointTrafficLog table


### Online endpoint failed requests  


Get the latest 100 failed inferencing requests to the online endpoint.  

```query
AmlOnlineEndpointTrafficLog
| where ResponseCode != "200" and ResponseCode != "100" 
| project
    TimeGenerated,
    Location,
    OperationName,
    Method,
    Path,
    Subscription = _SubscriptionId,
    AzureMLWorkspaceId,
    EndpointName,
    DeploymentName,
    Protocol,
    ResponseCode,
    ResponseCodeReason,
    ModelStatusCode,
    ModelStatusReason,
    RequestPayloadSize,
    ResponsePayloadSize,
    UserAgent,
    XRequestId,
    XMSClientRequestId,
    TotalDurationMs,
    RequestDurationMs,
    ResponseDurationMs,
    RequestThrottlingDelayMs,
    ResponseThrottlingDelayMs
| top 100 by TimeGenerated
```

