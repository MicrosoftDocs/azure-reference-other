---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/privateLinkServices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bytes In**<br><br>Total number of Bytes Out |`PLSBytesIn` |Count |Total |`PrivateLinkServiceId`|PT1M, PT1H |Yes|
|**Bytes Out**<br><br>Total number of Bytes Out |`PLSBytesOut` |Count |Total |`PrivateLinkServiceId`|PT1M, PT1H |Yes|
|**Nat Ports Usage**<br><br>Nat Ports Usage |`PLSNatPortsUsage` |Percent |Average |`PrivateLinkServiceId`, `PrivateLinkServiceIPAddress`|PT1M, PT1H |Yes|