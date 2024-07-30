---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Network/virtualHubs, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Scalability|**Bgp Peer Status**<br><br>1 - Connected, 0 - Not connected |`BgpPeerStatus` |Count |Maximum |`routeserviceinstance`, `bgppeerip`, `bgppeertype`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Scalability|**Count Of Routes Advertised To Peer**<br><br>Total number of routes advertised to peer |`CountOfRoutesAdvertisedToPeer` |Count |Maximum |`routeserviceinstance`, `bgppeerip`, `bgppeertype`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Scalability|**Count Of Routes Learned From Peer**<br><br>Total number of routes learned from peer |`CountOfRoutesLearnedFromPeer` |Count |Maximum |`routeserviceinstance`, `bgppeerip`, `bgppeertype`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Scalability|**Routing Infrastructure Units**<br><br>Total number of routing infrastructure units, which represent the virtual hub's capacity |`RoutingInfrastructureUnits` |Count |Maximum |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Traffic|**Spoke VM Utilization**<br><br>Number of deployed spoke VMs as a percentage of the total number of spoke VMs that the hub's routing infrastructure units can support |`SpokeVMUtilization` |Percent |Maximum |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Traffic|**Data Processed by the Virtual Hub Router**<br><br>Data on how much traffic traverses the virtual hub router in a given time period. Only the following flows use the virtual hub router: VNet to VNet (same hub and interhub) and branch to VNet (interhub). If a virtual hub is secured with routing intent, then these flows traverse the firewall instead of the hub router. |`VirtualHubDataProcessed` |Bytes |Total |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|