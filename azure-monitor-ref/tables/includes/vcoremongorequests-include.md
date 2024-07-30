---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: VCoreMongoRequests
---


| Column | Type | Description |
|---|---|---|
| ActivityId | string | The unique identifier (GUID) for this Mongo (vCore) request. |
| _BilledSize | real | The record size in bytes |
| ClientIp | string | The IP address of the client VM which issued the request. |
| ClusterName | string | Cluster name. |
| CollectionName | string | The name of the Cosmos DB container against which this request was issued. |
| DatabaseName | string | The name of the Cosmos DB database against which this request was issued. |
| DurationMs | real | The server-side execution time (in ms) for this request. |
| ErrorCode | int | The error code (if applicable) for this request. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The Mongo (vCore) operation that was executed. |
| PiiCommandText | string | Full text query for this Mongo (vCore) request. |
| RegionName | string | The region against which this request was issued. |
| RequestLength | real | The payload size (in bytes) of the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseLength | real | The payload size (in bytes) of the server response. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) of the Mongo (vCore) data plane request. |
| Type | string | The name of the table |
| UserAgent | string | The user agent suffix associated with the client issuing the request. |
| UserId | string | The user id associated with the client issuing the request. |
