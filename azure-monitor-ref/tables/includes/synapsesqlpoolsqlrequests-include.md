---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: SynapseSqlPoolSqlRequests
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| Command | string | The command of the SQL requests. |
| DistributionId | int | The distribution id of the SQL requests. |
| EndTime | datetime | The end time (UTC) for the SQL requests. |
| ErrorId | string | The error id of the SQL requests. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogicalServerName | string | The logical server name of the SQL DW. |
| OperationName | string | The operation associated with log record. |
| PdwNodeId | int | The PdwNodeId of the SQL requests. |
| RequestId | string | The request Id of the SQL requests. |
| ResourceGroup | string | The azure resourceGroup of the SQL DW. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RowCount | int | The row count of the SQL requests. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SpId | int | The sp id of the SQL requests. |
| StartTime | datetime | The startTime (UTC) of the SQL requests. |
| Status | string | The Status of the SQL requests. |
| StepIndex | int | The step index of the SQL requests. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
