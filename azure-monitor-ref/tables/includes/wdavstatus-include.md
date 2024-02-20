---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: WDAVStatus
---


| Column | Type | Description |
|---|---|---|
| ApplicationVersion | string |   |
| _BilledSize | real | The record size in bytes |
| CloudBlockLevel | string |   |
| Computer | string |   |
| ComputerID | string |   |
| DefinitionVersion | string |   |
| DetailedStatus | string |   |
| EngineVersion | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastDefinitionUpdateTime | datetime |   |
| LastScan | datetime |   |
| MoreInformation | string |   |
| OSName | string |   |
| ProtectionState | string |   |
| PuaMode | string |   |
| SampleSubmission | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| UpdateStatus | string |   |
