---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DeviceCleanup
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string |   |
| DeviceType | string |   |
| EventId | int |   |
| EventName | string |   |
| HealthServiceId | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ProviderId | string |   |
| SerialNumber | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| State | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
