---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ManagedNetworkFabric/internetGateways, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Proxy Connection Metrics|**Inbound active connections**<br><br>Count of inbound active connections |`InboundConnectionsActive` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|
|Proxy Connection Metrics|**Total inbound connections**<br><br>Count of inbound connections |`InboundConnectionsTotal` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|
|Proxy Connection Metrics|**Total outbound active connections**<br><br>Count of outbound active connections |`OutboundConnectionsActive` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|
|Proxy Connection Metrics|**Total outbound failed connections**<br><br>Count of outbound total failed connections |`OutboundConnectionsFail` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|
|Proxy Connection Metrics|**Total outbound connection timeouts**<br><br>Count of outbound connection timeouts |`OutboundConnectionsTimeout` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|
|Proxy Connection Metrics|**Total outbound connections**<br><br>Count of outbound total connections |`OutboundConnectionsTotal` |Count |Average, Maximum, Minimum |`nfcId`, `gatewayType`|PT1M |Yes|