---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/virtualHubs, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bgp Peer Status**<p><p>1 - Connected, 0 - Not connected |`BgpPeerStatus` |Count |Maximum |`routeserviceinstance`, `bgppeerip`, `bgppeertype`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Count Of Routes Advertised To Peer**<p><p>Total number of routes advertised to peer |`CountOfRoutesAdvertisedToPeer` |Count |Maximum |`routeserviceinstance`, `bgppeerip`, `bgppeertype`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Count Of Routes Learned From Peer**<p><p>Total number of routes learned from peer |`CountOfRoutesLearnedFromPeer` |Count |Maximum |`routeserviceinstance`, `bgppeerip`, `bgppeertype`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Data Processed by the Virtual Hub Router**<p><p>Data Processed by the Virtual Hub Router |`VirtualHubDataProcessed` |Bytes |Total |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|