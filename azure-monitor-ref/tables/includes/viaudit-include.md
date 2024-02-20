---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: VIAudit
---


| Column | Type | Description |
|---|---|---|
| AccountId | string | The Video Indexer account ID. |
| AccountName | string | The Video Indexer account name. |
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | The caller IP address. |
| Claims | dynamic | Caller claims details. |
| CorrelationId | string | A unique record identifier. |
| Description | string | The operation description. |
| DurationMs | int | The operation duration in milliseconds. |
| ExternalUserId | string | Caller external user Id. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The Video Indexer resource location. |
| OperationName | string | The name of the operation that triggered the event. |
| OperationVersion | string | The Video Indexer operations API version. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Signature | int | Http response signature of the operation, for example: 200, 401. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | Status of the operation, for example: Success, Failure, Warning, Informational, Partial Success. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| Type | string | The name of the table |
| Upn | string | Caller email. |
| VideoId | string | The Video Indexer video ID. |
| VideoIndexerResourceId | string | The Video Indexer resource ID. |
