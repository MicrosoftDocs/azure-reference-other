---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: microsoft.resources/subscriptions, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Latency**<br><br>Latency data for all requests to Azure Resource Manager |`Latency` |Seconds |Average |`IsCustomerOriginated`, `Method`, `Namespace`, `RequestRegion`, `ResourceType`, `StatusCode`, `StatusCodeClass`, `Microsoft.SubscriptionId`|PT1M |No|
|**Traffic**<br><br>Traffic data for all requests to Azure Resource Manager |`Traffic` |Count |Count |`IsCustomerOriginated`, `Method`, `Namespace`, `RequestRegion`, `ResourceType`, `StatusCode`, `StatusCodeClass`, `Microsoft.SubscriptionId`|PT1M |No|