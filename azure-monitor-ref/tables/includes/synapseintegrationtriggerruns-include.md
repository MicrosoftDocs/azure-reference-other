---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SynapseIntegrationTriggerRuns
---


| Column | Type | Description |
|---|---|---|
| Annotations | dynamic | The annotation details of the log record. |
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| CorrelationId | string | The correlationId for the log record. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The log type info level of the record. |
| Location | string | The location of the resource in the cloud where this log is originated. |
| OperationName | string | The operation associated with log record. |
| Parameters | dynamic | The parameter details of the pipeline run. |
| PipelineTenantId | string | The tenantId details of the pipeline run. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Start | datetime | The start time (UTC) of the trigger run. |
| Status | string | The Status of the SQL requests. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SystemParameters | dynamic | The system parameter details of the pipeline run. |
| Tags | dynamic | The associated tags of the log record. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TriggerEvent | string | The trigger id of the log record. |
| TriggerId | string | The trigger id of the log record. |
| TriggerName | string | The trigger name of the log record. |
| TriggerType | string | The trigger type of the log record. |
| Type | string | The type of the pipeline run. |
| UserProperties | dynamic | The user properties of the log record. |
