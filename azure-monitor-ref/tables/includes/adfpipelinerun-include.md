---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ADFPipelineRun
---


| Column | Type | Description |
|---|---|---|
| Annotations | string |   |
| _BilledSize | real | The record size in bytes |
| Category | string |   |
| CorrelationId | string |   |
| End | datetime |   |
| ErrorCode | string |   |
| ErrorMessage | string |   |
| EventMessage | string |   |
| FailureType | string |   |
| Input | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string |   |
| Location | string |   |
| OperationName | string |   |
| Output | string |   |
| Parameters | string |   |
| PipelineName | string |   |
| Predecessors | string |   |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RunId | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Start | datetime |   |
| Status | string |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SystemParameters | string |   |
| Tags | string |   |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| UserProperties | string |   |
