---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: WVDCheckpoints
---


| Column | Type | Description |
|---|---|---|
| ActivityType | string | The type of activity for which this checkpoint was reported. |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The correlation Id for the activity. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Name | string | The name of the checkpoint. |
| Parameters | dynamic | The parameters for the checkpoint. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Source | string | The component that emitted the checkpoint. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
| UserName | string | The user name for the activity associated with the checkpoint. |
