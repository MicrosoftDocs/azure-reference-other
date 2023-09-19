---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/privateLinkServices, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Bytes In<p><p>Total number of Bytes Out |`PLSBytesIn` |Count |Total |PrivateLinkServiceId|PT1M, PT1H |Yes|
|Bytes Out<p><p>Total number of Bytes Out |`PLSBytesOut` |Count |Total |PrivateLinkServiceId|PT1M, PT1H |Yes|
|Nat Ports Usage<p><p>Nat Ports Usage |`PLSNatPortsUsage` |Percent |Average |PrivateLinkServiceId, PrivateLinkServiceIPAddress|PT1M, PT1H |Yes|