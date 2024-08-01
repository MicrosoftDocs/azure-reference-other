---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ADFSSISPackageExecutableStatistics
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The name of the log that belongs to |
| CorrelationId | string | correlation id |
| DataFactoryName | string | Data factory name |
| EndTime | datetime | Executable end time |
| ExecutionDuration | int | Executable execution duration |
| ExecutionId | long | Execution id |
| ExecutionPath | string | Execution path |
| ExecutionResult | int | Execution result |
| ExecutionValue | dynamic | Execution value |
| IntegrationRuntimeName | string | Integration runtime name |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | Verbosity level of log |
| OperationName | string | The name of the operation represented by this event |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartTime | datetime | Executable start time |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the log |
| Type | string | The name of the table |
