---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: VIIndexing
---


| Column | Type | Description |
|---|---|---|
| AccountId | string | Video Indexer account ID. |
| AccountName | string | Video Indexer account name. |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | A unique record identifier. |
| DurationMs | int | The operation duration in milliseconds. |
| ErrorCode | string | The error code if the operation failed |
| ErrorDescription | string | The description of the error code . |
| ExternalUserId | string | Caller external user Id. |
| IndexingProperties | dynamic | Properties of the indexing operation request. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | Video Indexer resource location. |
| OperationName | string | The name of the operation that triggered the event. |
| OperationVersion | string | Video Indexer operations API version. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | Status of the operation, for example: Success, Failure, Warning, Informational or PartialSuccess. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| Type | string | The name of the table |
| Upn | string | Caller email. |
| VideoId | string | Video Indexer video ID. |
| VideoIndexerResourceId | string | Video Indexer resource ID. |
