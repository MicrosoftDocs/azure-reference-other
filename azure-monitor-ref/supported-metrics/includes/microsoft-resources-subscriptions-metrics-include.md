---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.resources/subscriptions, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Latency<p><p>Latency data for all requests to Azure Resource Manager |`Latency` |Seconds |Average |IsCustomerOriginated, Method, Namespace, RequestRegion, ResourceType, StatusCode, StatusCodeClass, Microsoft.SubscriptionId|PT1M |No|
|Traffic<p><p>Traffic data for all requests to Azure Resource Manager |`Traffic` |Count |Count |IsCustomerOriginated, Method, Namespace, RequestRegion, ResourceType, StatusCode, StatusCodeClass, Microsoft.SubscriptionId|PT1M |No|