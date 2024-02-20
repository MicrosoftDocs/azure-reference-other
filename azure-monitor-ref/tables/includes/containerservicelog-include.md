---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ContainerServiceLog
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Command | string |   |
| Computer | string |   |
| ContainerID | string |   |
| Image | string |   |
| ImageTag | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Repository | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |   |
| TimeOfCommand | datetime |   |
| Type | string | The name of the table |
