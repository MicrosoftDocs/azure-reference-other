---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/08/2024
ms.author: orens
author: osalzberg
ms.custom: CDBTableApiRequests
---


| Column | Type | Description |
|---|---|---|
| AccountName | string | The name of the Cosmos DB account against which this request was issued. |
| ActivityId | string | The unique identifier (GUID) for this Table API request. |
| Address | string | The IP address of the client that issued this request. |
| AuthorizationTokenType | string | The authorization token used for this request. |
| _BilledSize | real | The record size in bytes |
| ClientRequestId | string | The unique client request identifier (GUID) for this Table API request. |
| DurationMs | real | The server side execution time (in ms) for this request. |
| ErrorCode | string | The error code (if applicable) for this request. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The Table API operation that was executed. |
| PIICommandText | string | Full query text with parameters (if opted in) for this request. |
| RegionName | string | The region against which this request was issued. |
| RequestCharge | real | The RU (Request Unit) consumption for this request. |
| RequestLength | real | The payload size (in bytes) of the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseLength | real | The payload size (in bytes) of the server response. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | The name of the Cosmos DB table against which this request was issued. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) of the Table API data plane request. |
| Type | string | The name of the table |
| UserAgent | string | The user agent suffix of the client issuing the request. |
