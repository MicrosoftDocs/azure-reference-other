---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/virtualHubs, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Scalability|**Bgp Peer Status**<br><br>1 - Connected, 0 - Not connected |`BgpPeerStatus` |Count |Maximum |`routeserviceinstance`, `bgppeerip`, `bgppeertype`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Scalability|**Count Of Routes Advertised To Peer**<br><br>Total number of routes advertised to peer |`CountOfRoutesAdvertisedToPeer` |Count |Maximum |`routeserviceinstance`, `bgppeerip`, `bgppeertype`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Scalability|**Count Of Routes Learned From Peer**<br><br>Total number of routes learned from peer |`CountOfRoutesLearnedFromPeer` |Count |Maximum |`routeserviceinstance`, `bgppeerip`, `bgppeertype`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Traffic|**Data Processed by the Virtual Hub Router**<br><br>Data Processed by the Virtual Hub Router |`VirtualHubDataProcessed` |Bytes |Total |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|