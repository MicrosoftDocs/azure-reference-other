---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: FailedIngestion
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Database | string | The name of the database holding the target table |
| Details | string | Detailed description of the failure and error message |
| ErrorCode | string | The failure's error code |
| FailedOn | datetime | Time at which this ingest operation failed |
| FailureStatus | string | The failure's status. `Permanent`, or `RetryAttemptsExceeded` indicates that the operation exceeded the max retries or max time limit following a recurring transient error |
| IngestionSourceId | string | A unique identifier representing the ingested source |
| IngestionSourcePath | string | The path of the ingestion data sources or the Azure blob storage URI |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationId | string | The ingestion's operation ID |
| OriginatesFromUpdatePolicy | bool | Indicates whether or not the failure originate from an update policy |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The final state of this data ingestion operation |
| RootActivityId | string | The ingestion's activity ID |
| ShouldRetry | bool | Indicates whether or not the failure is transient and should be retried |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Table | string | The name of the target table into which the data is ingested |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
