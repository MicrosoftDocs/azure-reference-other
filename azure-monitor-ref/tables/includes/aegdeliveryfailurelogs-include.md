---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AegDeliveryFailureLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | Log category name. |
| EventSubscriptionName | string | Name of the event subscription. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | Log message for the user. |
| OperationName | string | Name of the operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SubResourceName | string | Name of the sub resource. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time when log was generated. |
| Type | string | The name of the table |
