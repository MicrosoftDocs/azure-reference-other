---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/28/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ContainerInventory
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Command | string |   |
| ComposeGroup | string |   |
| Computer | string |   |
| ContainerHostname | string |   |
| ContainerID | string |   |
| ContainerState | string |   |
| CreatedTime | datetime |   |
| EnvironmentVar | string |   |
| ExitCode | int |   |
| FinishedTime | datetime |   |
| Image | string |   |
| ImageID | string |   |
| ImageTag | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Links | string |   |
| Name | string |   |
| Ports | string |   |
| Repository | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartedTime | datetime |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
