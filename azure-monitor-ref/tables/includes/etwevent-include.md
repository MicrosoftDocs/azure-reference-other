---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ETWEvent
---


| Column | Type | Description |
|---|---|---|
| AzureDeploymentID | string |   |
| _BilledSize | real | The record size in bytes |
| ChannelName | string |   |
| Computer | string |   |
| EventId | int |   |
| EventMessage | string |   |
| EventSourceName | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| KeywordName | string |   |
| Level | string |   |
| Message | string |   |
| OpcodeName | string |   |
| Pid | int |   |
| ProviderGuid | string |   |
| Role | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TaskName | string |   |
| Tid | int |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
