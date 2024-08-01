---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: microsoft.network/p2svpngateways, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Gateway P2S Bandwidth**<br><br>Point-to-site bandwidth of a gateway in bytes per second |`P2SBandwidth` |BytesPerSecond |Average |`Instance`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**P2S Connection Count**<br><br>Point-to-site connection count of a gateway |`P2SConnectionCount` |Count |Total |`Protocol`, `Instance`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Routing|**User Vpn Route Count**<br><br>Count of P2S User Vpn routes learned by gateway |`UserVpnRouteCount` |Count |Total |`RouteType`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|