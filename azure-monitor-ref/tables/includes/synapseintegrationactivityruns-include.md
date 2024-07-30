---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: SynapseIntegrationActivityRuns
---


| Column | Type | Description |
|---|---|---|
| ActivityName | string | The name of the activity run. |
| ActivityRunId | string | The run id of the activity run. |
| ActivityType | string | The type of the activity run. |
| Annotations | dynamic | The annotation details of the log record. |
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| CorrelationId | string | The correlationId for the log record. |
| EffectiveIntegrationRuntime | string | The effective integration runtime the activity run job. |
| End | datetime | The end time (UTC) for the activity run. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The log type info level of the record. |
| Location | string | The location of the resource in the cloud where this log is originated. |
| OperationName | string | The operation associated with log record. |
| PipelineName | string | The pipeline name of the activity flow. |
| PipelineRunId | string | The pipeline runId of the activity flow. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Start | datetime | The start time (UTC) of the activity run. |
| Status | string | The Status of the sql requests. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | dynamic | The associated tags of the log record. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserProperties | dynamic | The user properties of the log record. |
