---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: VMBoundPort
---


| Column | Type | Description |
|---|---|---|
| AgentId | string | Unique agent GUID for the agent reporting data on the server. |
| _BilledSize | real | The record size in bytes |
| BytesReceived | long | Bytes received on the port |
| BytesSent | long | Bytes sent on the port |
| Computer | string | Name of the server |
| Ip | string | Port IP address. Can be wildcard IP 0.0.0.0. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsWildcardBind | bool | Specifies whether connection made as a wildcard bind request. |
| LinksEstablished | long | Count of links established on the port. |
| LinksLive | long | Count of live links at the end of the time period recorded. |
| LinksTerminated | long | Count of terminated links over the time periof recorded. |
| Machine | string | Unique identifier to the machine in the ServiceMapComputer_CL table. |
| Port | int | Port number. |
| PortId | string | Port ID. |
| Process | string | Identity of the process or group of processes that the port is associated with. |
| ProcessName | string | Unique identifier for the process in the ServiceMapProcess_CL table. |
| Protocol | string | The protocol. Example tcp or udp (only tcp is currently supported). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Responses | long | Count of responses in the time period recorded. |
| ResponseTimeMax | long | Measurement of the maximum time between first and last byte received. |
| ResponseTimeMin | long | Measurement of the minimum time between first and last byte received. |
| ResponseTimeSum | long | Measurement of the total time between first and last byte received |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
