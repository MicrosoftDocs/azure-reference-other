---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/trafficManagerProfiles, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Endpoint Status by Endpoint**<br><br>1 if an endpoint's probe status is "Enabled", 0 otherwise. |`ProbeAgentCurrentEndpointStateByProfileResourceId` |Count |Maximum |`EndpointName`|PT1M, PT1H |Yes|
|**Queries by Endpoint Returned**<br><br>Number of times a Traffic Manager endpoint was returned in the given time frame |`QpsByEndpoint` |Count |Total |`EndpointName`|PT1M, PT1H |Yes|