---
title: Azure Monitor Logs reference - UAProposedActionPlan
description: Reference for UAProposedActionPlan table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/10/2023
---

# UAProposedActionPlan

 

## Categories

- Desktop Analytics
## Solutions

- Upgrade Readiness




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real | The record size in bytes |
| ComputersUnblocked | int |  |
| CumulativeUnblocked | int |  |
| CumulativeUnblockedPct | real |  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| ItemHardwareID | string |  |
| ItemLanguage | string |  |
| ItemName | string |  |
| ItemRank | int |  |
| ItemType | string |  |
| ItemVendor | string |  |
| ItemVersion | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UpgradeDecision | string |  |
