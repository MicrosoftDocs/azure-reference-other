---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.network/p2svpngateways, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Gateway P2S Bandwidth<p><p>Point-to-site bandwidth of a gateway in bytes per second |`P2SBandwidth` |BytesPerSecond |Average |Instance|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|P2S Connection Count<p><p>Point-to-site connection count of a gateway |`P2SConnectionCount` |Count |Total |Protocol, Instance|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|User Vpn Route Count<p><p>Count of P2S User Vpn routes learned by gateway |`UserVpnRouteCount` |Count |Total |RouteType, Instance|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|