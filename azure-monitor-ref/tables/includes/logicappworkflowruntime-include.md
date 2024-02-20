---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: LogicAppWorkflowRuntime
---


| Column | Type | Description |
|---|---|---|
| ActionName | string | The name of the workflow action. |
| ActionTrackingId | string | The unique ID of the workflow action. |
| _BilledSize | real | The record size in bytes |
| ClientKeywords | string | The client keywords sent through the header. |
| ClientTrackingId | string | The unique ID of the client. |
| Code | string | The HTTP status code of the request. |
| EndTime | datetime | The end time (UTC) of the operation. |
| Error | string | The error message of this operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The geographical run location of the workflow. |
| OperationName | string | The name of this operation. |
| OriginRunId | string | The unique ID of the original workflow run, only relevant for resubmission scenarios. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RetryHistory | string | The retry history of the workflow action. |
| RunId | string | The unique ID of the workflow run. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartTime | datetime | The start time (UTC) of the operation. |
| Status | string | The status of the operation, e.g. Succeeded, Failed, Skipped, Ignored. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string | The custom tags associated with the workflow. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TrackedProperties | string | The custom tracked properties. |
| TriggerName | string | The name of the workflow trigger. |
| Type | string | The name of the table |
| WorkflowId | string | The unique ID of the workflow. |
| WorkflowName | string | The name of the workflow. |
