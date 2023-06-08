---
title: Azure Monitor Logs reference - UASysReqIssue
description: Reference for UASysReqIssue table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# UASysReqIssue

 

## Categories

- Desktop Analytics
## Solutions

- Upgrade Readiness




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Computer | string |  |
| ComputerID | string |  |
| Guidance | string |  |
| _IsBillable | string |  |
| Issue | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| SysReqType | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UpgradeAssessment | string |  |
