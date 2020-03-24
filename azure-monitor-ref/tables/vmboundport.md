---
title: Azure Monitor Logs reference - VMBoundPort
description: Reference for VMBoundPort table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# VMBoundPort

 Traffic for open server ports on the monitored machine.

## Categories

- Virtual Machines
## Solutions

- InfrastructureInsights
- Service Map
- VMInsights
## Resource types

- Virtual machine
- Virtual machine scale set




## Columns

|Column|Type|Description|
|---|---|---|
|TimeGenerated|datetime|Date and time the record was created.|
|Computer|string|Name of the server|
|ProcessName|string|Unique identifier for the process in the ServiceMapProcess_CL table.|
|Ip|string|Port IP address. Can be wildcard IP 0.0.0.0.|
|Port|int|Port number.|
|Protocol|string|The protocol. Example tcp or udp (only tcp is currently supported).|
|IsWildcardBind|bool|Specifies whether connection made as a wildcard bind request.|
|BytesSent|long|Bytes sent on the port|
|BytesReceived|long|Bytes received on the port|
|LinksLive|long|Count of live links at the end of the time period recorded.|
|LinksTerminated|long|Count of terminated links over the time periof recorded.|
|LinksEstablished|long|Count of links established on the port.|
|Responses|long|Count of responses in the time period recorded.|
|ResponseTimeSum|long|Measurement of the total time between first and last byte received|
|ResponseTimeMin|long|Measurement of the minimum time between first and last byte received.|
|ResponseTimeMax|long|Measurement of the maximum time between first and last byte received.|
|PortId|string|Port ID.|
|Machine|string|Unique identifier to the machine in the ServiceMapComputer_CL table.|
|Process|string|Identity of the process or group of processes that the port is associated with.|
|AgentId|string|Unique agent GUID for the agent reporting data on the server.|
|SourceSystem|string|Value is OpsManager for all records.|
|Type|string||
|_ResourceId|string||
