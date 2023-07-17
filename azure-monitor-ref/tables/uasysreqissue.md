---
title: Azure Monitor Logs reference - UASysReqIssue
description: Reference for UASysReqIssue table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/17/2023
---

# UASysReqIssue

 

## Categories

- Desktop Analytics
## Solutions

- Upgrade Readiness




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real | The record size in bytes |
| Computer | string |  |
| ComputerID | string |  |
| Guidance | string |  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| Issue | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| SysReqType | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UpgradeAssessment | string |  |
