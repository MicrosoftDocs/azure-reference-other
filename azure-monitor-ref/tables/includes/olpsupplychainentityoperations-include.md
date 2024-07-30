---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: OLPSupplyChainEntityOperations
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientApplicationId | string | Application ID of the client making the API request. |
| ClientName | string | Name of the client making the API request. |
| ClientObjectId | string | Object ID of the client making the API request. |
| ClientTenantId | string | Tenant ID of the client making the API request. |
| CorrelationId | string | Unique identifier to be used to correlate logs. |
| CustomRequestAttributes | dynamic | Client defined arbitrary data in the API request. |
| DurationMs | real | Time it took to service the REST API request, in milliseconds. |
| HttpStatusCode | int | HTTP status code of the API response. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The operation name for which the log entry was created. |
| RequestBody | dynamic | Request body of the API calls. |
| RequestId | string | Unique identifier to be used to correlate request logs. |
| RequestMethod | string | HTTP method of the API request. |
| RequestUri | string | URI of the API request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseBody | dynamic | Request body of the API calls. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
