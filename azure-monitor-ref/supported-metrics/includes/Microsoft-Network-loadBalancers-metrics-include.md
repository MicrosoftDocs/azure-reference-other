---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/loadBalancers, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Allocated SNAT Ports**<p><p>Total number of SNAT ports allocated within time period |`AllocatedSnatPorts` |Count |Average |`FrontendIPAddress`, `BackendIPAddress`, `ProtocolType`, `IsAwaitingRemoval`|PT1M |No|
|**Byte Count**<p><p>Total number of Bytes transmitted within time period |`ByteCount` |Bytes |Total |`FrontendIPAddress`, `FrontendPort`, `Direction`|PT1M |Yes|
|**Health Probe Status**<p><p>Average Load Balancer health probe status per time duration |`DipAvailability` |Count |Average |`ProtocolType`, `BackendPort`, `FrontendIPAddress`, `FrontendPort`, `BackendIPAddress`|PT1M |Yes|
|**Health Probe Status**<p><p>Azure Cross-region Load Balancer backend health and status per time duration |`GlobalBackendAvailability` |Count |Average |`FrontendIPAddress`, `FrontendPort`, `BackendIPAddress`, `ProtocolType`, `FrontendRegion`, `BackendRegion`|PT1M |Yes|
|**Packet Count**<p><p>Total number of Packets transmitted within time period |`PacketCount` |Count |Total |`FrontendIPAddress`, `FrontendPort`, `Direction`|PT1M |Yes|
|**SNAT Connection Count**<p><p>Total number of new SNAT connections created within time period |`SnatConnectionCount` |Count |Total |`FrontendIPAddress`, `BackendIPAddress`, `ConnectionState`|PT1M |Yes|
|**SYN Count**<p><p>Total number of SYN Packets transmitted within time period |`SYNCount` |Count |Total |`FrontendIPAddress`, `FrontendPort`, `Direction`|PT1M |Yes|
|**Used SNAT Ports**<p><p>Total number of SNAT ports used within time period |`UsedSnatPorts` |Count |Average |`FrontendIPAddress`, `BackendIPAddress`, `ProtocolType`, `IsAwaitingRemoval`|PT1M |No|
|**Data Path Availability**<p><p>Average Load Balancer data path availability per time duration |`VipAvailability` |Count |Average |`FrontendIPAddress`, `FrontendPort`|PT1M |Yes|