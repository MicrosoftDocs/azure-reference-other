---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: MAApplicationHealthAlternativeVersions
---


| Column | Type | Description |
|---|---|---|
| AdoptionStatus | string |   |
| AppLanguage | string |   |
| AppName | string |   |
| AppVendor | string |   |
| AppVersion | string |   |
| _BilledSize | real | The record size in bytes |
| DevicesWithCrashesPercentOnTargetForCommercial | real |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OSVersion | string |   |
| ProgramId | string |   |
| SessionsWithCrashesPercentOnTargetForCommercial | real |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
