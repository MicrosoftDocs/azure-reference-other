---
title: Azure Monitor Logs reference - MAOfficeAddin
description: Reference for MAOfficeAddin table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# MAOfficeAddin



## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

| Column | Type | Description |
|---|---|---|
| AddinInstanceId | string |   |
| AddinName | string |   |
| AddinProducts | string |   |
| AddinPublisher | string |   |
| AddinRemarks | string |   |
| AddinSupportStatementUrl | string |   |
| AddinSupportStatus | string |   |
| AddinVersion | string |   |
| _BilledSize | real | The record size in bytes |
| Importance | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TestOwner | string |   |
| TestPlan | string |   |
| TimeGenerated | datetime |   |
| TotalInstalls | int |   |
| Type | string | The name of the table |
