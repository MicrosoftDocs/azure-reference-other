---
ms.service: azure-monitor
ms.topic: include
ms.date: 11/13/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: LASummaryLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| BinSize | int | The time ranges summarization is performed in minutes. For example, when bin is 60, summarization is performed every 60 minutes. |
| BinStartTime | datetime | The bin start time (UTC). For example, value can be 2023-01-01T2:00:00.000Z for bin processed between 2:00 - 3:00. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | An error message when applicable. |
| QueryDurationMs | long | The execution duration in milliseconds. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultsRecordCount | long | The number of records returned in aggregation. |
| RuleLastModifiedTime | datetime | The time the rule last modified. Can be used to reason changes in results, duration, etc. |
| RuleName | string | The rule name. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | The bin execution status. Can be Started, Succeeded or Failed. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The bin execution start time (UTC). It represents the time bin processing started, and decoupled from bin time range. For example, TimeGenerated can be 2023-01-01T3:05:10.123Z when processing hourly bin between 2:00 - 3:00. |
| Type | string | The name of the table |
