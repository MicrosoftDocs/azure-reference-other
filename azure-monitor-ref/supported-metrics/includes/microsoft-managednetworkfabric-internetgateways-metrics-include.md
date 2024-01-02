---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ManagedNetworkFabric/internetGateways, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Inbound active connections**<p><p>Count of inbound active connections |`InboundConnectionsActive` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|
|**Total inbound connections**<p><p>Count of inbound connections |`InboundConnectionsTotal` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|
|**Total outbound active connections**<p><p>Count of outbound active connections |`OutboundConnectionsActive` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|
|**Total outbound failed connections**<p><p>Count of outbound total failed connections |`OutboundConnectionsFail` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|
|**Total outbound connection timeouts**<p><p>Count of outbound connection timeouts |`OutboundConnectionsTimeout` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|
|**Total outbound connections**<p><p>Count of outbound total connections |`OutboundConnectionsTotal` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|