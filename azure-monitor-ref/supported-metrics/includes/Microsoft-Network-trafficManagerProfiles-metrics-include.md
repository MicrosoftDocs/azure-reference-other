---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/trafficManagerProfiles, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Endpoint Status by Endpoint<p><p>1 if an endpoint's probe status is "Enabled", 0 otherwise. |`ProbeAgentCurrentEndpointStateByProfileResourceId` |Count |Maximum |EndpointName|PT1M, PT1H |Yes|
|Queries by Endpoint Returned<p><p>Number of times a Traffic Manager endpoint was returned in the given time frame |`QpsByEndpoint` |Count |Total |EndpointName|PT1M, PT1H |Yes|