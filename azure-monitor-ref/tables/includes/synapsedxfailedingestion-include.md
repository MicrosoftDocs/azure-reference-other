---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: SynapseDXFailedIngestion
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Database | string | The name of the database holding the target table |
| Details | string | Details of the failure |
| ErrorCode | string | Failure's error code like 'BadRequest_EmptyBlob' |
| FailedOn | datetime | The time this ingest operation failed |
| FailureStatus | string | Failure's status like 'Permanent' |
| IngestionSourceId | string | The ID of the ingestion source |
| IngestionSourcePath | string | Azure blob storage URI |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationId | string | The ingestion's operation ID |
| OriginatesFromUpdatePolicy | bool | Indicates if the failure originates from an Update Policy |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | Final state of this data ingestion operation like 'Failed' |
| RootActivityId | string | The ingestion's activity ID Used for debugging issues |
| ShouldRetry | bool | Indicates if the failure is temporary and the operation should be retried |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Table | string | The name of the target table the data is ingested into |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) when this event was generated |
| Type | string | The name of the table |
