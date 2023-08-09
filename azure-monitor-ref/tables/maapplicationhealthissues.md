---
title: Azure Monitor Logs reference - MAApplicationHealthIssues
description: Reference for MAApplicationHealthIssues table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# MAApplicationHealthIssues



## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

| Column | Type | Description |
|---|---|---|
| AppFileDisplayName | string |   |
| AppFileName | string |   |
| AppFileVersion | string |   |
| AppLanguage | string |   |
| AppName | string |   |
| AppVendor | string |   |
| AppVersion | string |   |
| _BilledSize | real | The record size in bytes |
| DeviceId | string |   |
| DiagnosticSignature | string |   |
| FailureId | string |   |
| FailureInstanceCount | int |   |
| FirstFailureDate | datetime |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastFailureDate | datetime |   |
| OSVersion | string |   |
| ProgramId | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
