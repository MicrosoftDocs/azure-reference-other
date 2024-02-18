---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ACRConnectedClientList
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CacheName | string | The name of the Azure Cache for Redis instance. |
| ClientCount | int | The number of Redis client connections from the associated IP address. |
| ClientIp | string | The Redis client IP address. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The location (region) the Azure Cache for Redis instance was accessed in. |
| OperationName | string | The Redis operation associated with the log record. |
| PrivateLinkIpv6 | string | The Redis client private link IPv6 address (if applicable). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RoleInstance | string | The role instance which logged the client list. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp of when the log was generated in UTC. |
| Type | string | The name of the table |
