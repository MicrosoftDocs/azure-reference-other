---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: SynapseSqlPoolExecRequests
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| ClassifierName | string | The classifier name of the execution requests. |
| ClientCorrelationId | string | The correlation set by client/user. |
| Command | string | The SQL command of the execution requests. |
| DatabaseId | string | The databaseId of the execution requests. |
| EndCompileTime | datetime | The end compile time (UTC) of the execution requests. |
| EndTime | datetime | The end time (UTC) for the execution requests. |
| ErrorId | string | The errorId of the execution requests. |
| ExplainOutput | string | The output explain of the execution requests. |
| Importance | string | The importance of the execution requests. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Label | string | The label of the execution requests. |
| LogicalServerName | string | The logical server name of the SQL DW. |
| OperationName | string | The operation associated with log record. |
| RequestId | string | The requestId of the execution requests. |
| ResourceAllocationPercent | string | The resource allocation percent of the execution requests. |
| ResourceClass | string | The resource class of the execution requests. |
| ResourceGroup | string | The azure resourceGroup of the SQL DW. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultCacheHit | string | The result cache hit of the execution requests. |
| RootQueryId | string | The rootQueryId of the execution requests. |
| ScopeDepth | int | The scope depth of the execution requests. |
| SessionId | string | The Session ID of the SQL pool instance. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartTime | datetime | The startTime (UTC) of the execution requests. |
| StatementType | string | The statement type of the execution requests. |
| Status | string | The status of the execution requests. |
| SubmitTime | datetime | The submitTime (UTC) of the execution requests. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
