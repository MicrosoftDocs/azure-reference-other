---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/08/2024
ms.author: orens
author: osalzberg
ms.custom: CDBCassandraRequests
---


| Column | Type | Description |
|---|---|---|
| AccountName | string | The name of the Cosmos DB account against which this request was issued. |
| ActivityId | string | The unique identifier (GUID) for this Cassandra API request. |
| Address | string | The IP address of the client that issued this request. |
| AuthorizationTokenType | string | The authorization token used for this request. |
| _BilledSize | real | The record size in bytes |
| CollectionName | string | The name of the Cosmos DB table/container against which this request was issued. |
| DatabaseName | string | The name of the Cosmos DB database against which this request was issued. |
| DurationMs | real | The server side execution time (in ms) for this request. |
| ErrorCode | string | The error code (if applicable) for this request. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The Cassandra API operation that was executed. |
| PIICommandText | string | Full query text with parameters (if opted in) for this request. |
| RateLimitingDelayMs | real | The estimated time (in ms) spent in retrying due to rate limited operations. |
| RegionName | string | The region against which this request was issued. |
| RequestCharge | real | The RU (Request Unit) consumption for this request. |
| RequestLength | real | The payload size (in bytes) of the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseLength | real | The payload size (in bytes) of the server response. |
| RetriedDueToRateLimiting | bool | Boolean flag indicating if this request was retried server side due to throttles. |
| RetryCount | int | The number of server side retries issued for this request. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) of the Cassandra API data plane request. |
| Type | string | The name of the table |
| UserAgent | string | The user agent suffix of the client issuing the request. |
