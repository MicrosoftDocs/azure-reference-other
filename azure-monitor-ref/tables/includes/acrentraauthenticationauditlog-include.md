---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/02/2024
ms.author: orens
author: osalzberg
ms.custom: ACREntraAuthenticationAuditLog
---


| Column | Type | Description |
|---|---|---|
| Authentication | string | Authentication result. |
| _BilledSize | real | The record size in bytes |
| CacheName | string | The name of the Azure Cache for Redis instance. |
| ClientId | string | Client identifier. |
| ClientName | string | Client name. |
| IpAddress | string | The IP address and port associated with the log event. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Lifetime | string | Duration of Microsoft Entra authentication validity, measured in Milliseconds from the initial connection. |
| Location | string | The location (region) the Azure Cache for Redis instance was accessed in. |
| Message | string | The message associated with the log event. |
| OperationName | string | The Redis operation associated with the log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RoleInstance | int | The role instance associated with the log event. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp of when the log was generated in UTC. |
| Type | string | The name of the table |
| Username | string | The user's identifier or username. |
