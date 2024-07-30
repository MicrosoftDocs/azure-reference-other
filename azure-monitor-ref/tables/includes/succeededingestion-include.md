---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: SucceededIngestion
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Database | string | The name of the database holding the target table |
| IngestionSourceId | string | A unique identifier representing the ingested source |
| IngestionSourcePath | string | The path of the ingestion data sources or the Azure blob storage URI |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationId | string | The ingestion's operation ID |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The final state of this data ingestion operation |
| RootActivityId | string | The ingestion's activity ID |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SucceededOn | datetime | Time at which this ingest operation successfully ended |
| Table | string | The name of the target table into which the data is ingested |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
