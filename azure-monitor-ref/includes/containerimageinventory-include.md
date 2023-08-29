---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/28/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ContainerImageInventory
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string |   |
| Failed | int |   |
| Image | string |   |
| ImageID | string |   |
| ImageSize | string |   |
| ImageTag | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Paused | int |   |
| Repository | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Running | int |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Stopped | int |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |   |
| TotalContainer | long |   |
| Type | string | The name of the table |
| VirtualSize | string |   |
