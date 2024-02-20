---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SynapseSqlPoolDmsWorkers
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| BytesProcessed | int | The bytes processed of the DMS workers. |
| Category | string | The category of the log. |
| CpuTime | int | The cpu time for the DMS workers. |
| DestinationInfo | string | The row count of the DMS workers. |
| DistributionId | int | The distribution id of the DMS workers. |
| DmsCpuId | int | The DMS cpu Id for the DMS workers. |
| DmsStepIndex | int | The DMS step index of the DMS workers. |
| EndTime | datetime | The end time (UTC) for the DMS workers. |
| ErrorId | string | The errorId of the DMS workers. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogicalServerName | string | The logical server name of the SQL DW. |
| OperationName | string | The operation associated with log record. |
| PdwNodeId | int | The pdw node id of the DMS workers. |
| RequestId | string | The requestId of the DMS workers. |
| ResourceGroup | string | The azure resourceGroup of the SQL DW. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RowsProcessed | int | The rows processed of the DMS workers. |
| SourceInfo | string | The row count of the DMS workers. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SqlSpId | int | The SQL  Sp Id for the DMS workers. |
| StartTime | datetime | The startTime (UTC) of the DMS workers. |
| Status | string | The status of the DMS workers. |
| StepIndex | int | The step index of the DMS workers. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The type of the DMS workers. |
