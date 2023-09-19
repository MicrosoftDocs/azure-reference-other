---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.network/expressroutegateways, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Bits In Per Second<p><p>Bits per second ingressing Azure via ExpressRoute Gateway which can be further split for specific connections |`ErGatewayConnectionBitsInPerSecond` |BitsPerSecond |Average |ConnectionName|PT1M |No|
|Bits Out Per Second<p><p>Bits per second egressing Azure via ExpressRoute Gateway which can be further split for specific connections |`ErGatewayConnectionBitsOutPerSecond` |BitsPerSecond |Average |ConnectionName|PT1M |No|
|Active Flows<p><p>Number of Active Flows on ExpressRoute Gateway |`ExpressRouteGatewayActiveFlows` |Count |Average, Minimum, Maximum |roleInstance|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Bits Received Per second<p><p>Total Bits received on ExpressRoute Gateway per second |`ExpressRouteGatewayBitsPerSecond` |BitsPerSecond |Average, Minimum, Maximum |roleInstance|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Count Of Routes Advertised to Peer<p><p>Count Of Routes Advertised To Peer by ExpressRoute Gateway |`ExpressRouteGatewayCountOfRoutesAdvertisedToPeer` |Count |Maximum |roleInstance, BgpPeerAddress|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Count Of Routes Learned from Peer<p><p>Count Of Routes Learned From Peer by ExpressRoute Gateway |`ExpressRouteGatewayCountOfRoutesLearnedFromPeer` |Count |Maximum |roleInstance, BgpPeerAddress|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|CPU utilization<p><p>CPU Utilization of the ExpressRoute Gateway |`ExpressRouteGatewayCpuUtilization` |Percent |Average, Minimum, Maximum |roleInstance|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Frequency of Routes change<p><p>Frequency of Routes change in ExpressRoute Gateway |`ExpressRouteGatewayFrequencyOfRoutesChanged` |Count |Total |roleInstance|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Max Flows Created Per Second<p><p>Maximum Number of Flows Created Per Second on ExpressRoute Gateway |`ExpressRouteGatewayMaxFlowsCreationRate` |CountPerSecond |Maximum |roleInstance, direction|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Number of VMs in the Virtual Network<p><p>Number of VMs in the Virtual Network |`ExpressRouteGatewayNumberOfVmInVnet` |Count |Maximum |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Packets received per second<p><p>Total Packets received on ExpressRoute Gateway per second |`ExpressRouteGatewayPacketsPerSecond` |CountPerSecond |Average, Minimum, Maximum |roleInstance|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|