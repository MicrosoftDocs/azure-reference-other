---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ChaosStudioExperimentEventLogs
---


| Column | Type | Description |
|---|---|---|
| Action | string | Fault name of the action. |
| _BilledSize | real | The record size in bytes |
| Branch | string | Experiment Branch ID of the span. |
| CorrelationId | string | The ID for the Experiment run. |
| Error | string | Error detail of the span. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The location of the experiment. |
| OperationName | string | The operation associated with event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SeverityLevel | string | Severity level of the event, one of: Informational, Warning, Error, Critical. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SpanType | string | One of experiment span types: Experiment, Branch, Step, or Action. |
| Status | string | Status of the span. For SpanType of Step or Branch, status is one of Started or Stopped. For Action, status is one of Started, Stopping, Stopped or Failed. For Experiment run, status is one of Started, Complete, Cancelling, Cancelled, Failed. |
| Step | string | Experiment Step ID of the span. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Target | string | Target resource ID of the fault. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| Type | string | The name of the table |
