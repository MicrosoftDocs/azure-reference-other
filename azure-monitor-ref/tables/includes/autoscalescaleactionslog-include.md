---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AutoscaleScaleActionsLog
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string |   |
| CorrelationId | string |   |
| CreatedAsyncScaleActionJob | bool |   |
| CreatedAsyncScaleActionJobId | string |   |
| CurrentInstanceCount | int |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NewInstanceCount | int |   |
| OperationName | string |   |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string |   |
| ResultType | string |   |
| ScaleActionMessage | string |   |
| ScaleActionOperationId | string |   |
| ScaleActionOperationStatus | string |   |
| ScaleDirection | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetResourceId | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
