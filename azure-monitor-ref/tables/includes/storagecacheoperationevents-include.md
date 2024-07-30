---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: StorageCacheOperationEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | Unique identifier to be used to correlate logs, if available. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The region of the resource associated with the event. |
| OperationName | string | The operation name for which the log entry was created. |
| PrimingJobName | string | Name of the priming job associated with the operation, if available. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseCode | int | HTTP status of API request. |
| ResultDescription | string | Details about the result, if available. |
| ResultType | string | Result of the REST API request. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StorageTargetName | string | Name of the storage target associated with the operation, if available. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
