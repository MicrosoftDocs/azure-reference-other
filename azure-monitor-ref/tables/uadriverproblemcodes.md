---
title: Azure Monitor Logs reference - UADriverProblemCodes
description: Reference for UADriverProblemCodes table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# UADriverProblemCodes

 

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
| DriverAvailability | string |  |
| DriverDate | string |  |
| DriverName | string |  |
| DriverVendor | string |  |
| DriverVersion | string |  |
| Guidance | string |  |
| HardwareID | string |  |
| HardwareName | string |  |
| HardwareType | string |  |
| _IsBillable | string |  |
| ProblemCode | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
