---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: REDConnectionEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientIp | string | The Redis client IP address. |
| ConnectionId | long | Unique connection ID assigned by Redis. |
| EventEpochTime | long | The unix timestamp (number of seconds since January 1, 1970) when the event happened in UTC. This can be converted to datetime format using function unixtime_seconds_todatetime in log analytics workspace. |
| EventStatus | int | Results of an authentication request as a status code (only applicable for authentication event). |
| EventType | string | Type of connection event(new_conn/auth/close_conn). |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The location (i.e. region) of the Azure Cache for Redis Enterprise instance that was accessed. |
| OperationName | string | The Redis operation associated with the log record. |
| PrivateLinkIPv6 | string | The Redis client private link IPv6 address (if applicable). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when event audit log was captured. |
| Type | string | The name of the table |
