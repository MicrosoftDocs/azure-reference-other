---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ApiManagementGatewayLogs
---


| Column | Type | Description |
|---|---|---|
| ApiId | string |   |
| ApimSubscriptionId | string |   |
| ApiRevision | string |   |
| BackendId | string |   |
| BackendMethod | string |   |
| BackendProtocol | string |   |
| BackendRequestBody | string | Backend request body |
| BackendRequestHeaders | dynamic |   |
| BackendResponseBody | string | Backend response body |
| BackendResponseCode | int |   |
| BackendResponseHeaders | dynamic |   |
| BackendTime | long |   |
| BackendUrl | string |   |
| _BilledSize | real | The record size in bytes |
| Cache | string |   |
| CacheTime | long |   |
| CallerIpAddress | string |   |
| Category | string |   |
| ClientProtocol | string |   |
| ClientTime | long |   |
| ClientTlsVersion | string |   |
| CorrelationId | string |   |
| Errors | dynamic |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsMasterTrace | bool | Indication if the request trace was created with the master subscription |
| IsRequestSuccess | bool |   |
| IsTraceAllowed | bool | Indication if the requested trace was allowed |
| IsTraceExpired | bool | Indication if the requested trace has expired and is not granted |
| IsTraceRequested | bool | Indication if the caller has requested to create a request trace |
| LastErrorElapsed | long |   |
| LastErrorMessage | string |   |
| LastErrorReason | string |   |
| LastErrorScope | string |   |
| LastErrorSection | string |   |
| LastErrorSource | string |   |
| Method | string |   |
| OperationId | string |   |
| OperationName | string |   |
| ProductId | string |   |
| Region | string |   |
| RequestBody | string | Client request body |
| RequestHeaders | dynamic |   |
| RequestSize | int |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseBody | string | Gateway response body |
| ResponseCode | int |   |
| ResponseHeaders | dynamic |   |
| ResponseSize | int |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |   |
| Timestamp | datetime |   |
| TotalTime | long |   |
| TraceRecords | dynamic | Records emitted by trace policies |
| Type | string | The name of the table |
| Url | string |   |
| UserId | string |   |
| WorkspaceId | string | ID of a workspace for which the request API operation is a part of |
