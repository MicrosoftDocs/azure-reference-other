---
title: Azure Monitor Logs reference - UAOfficeAddIn
description: Reference for UAOfficeAddIn table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# UAOfficeAddIn

 

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
| _IsBillable | string |  |
| OfficeAddInDescription | string |  |
| OfficeAddInID | string |  |
| OfficeAddInName | string |  |
| OfficeProduct | string |  |
| OfficeProductVersion | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
