---
title: Azure Monitor Logs reference - WDAVStatus
description: Reference for WDAVStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# WDAVStatus

 

## Categories

- Desktop Analytics
## Solutions

- Update Compliance




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationVersion | string |  |
| _BilledSize | real |  |
| CloudBlockLevel | string |  |
| Computer | string |  |
| ComputerID | string |  |
| DefinitionVersion | string |  |
| DetailedStatus | string |  |
| EngineVersion | string |  |
| _IsBillable | string |  |
| LastDefinitionUpdateTime | datetime |  |
| LastScan | datetime |  |
| MoreInformation | string |  |
| OSName | string |  |
| ProtectionState | string |  |
| PuaMode | string |  |
| SampleSubmission | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UpdateStatus | string |  |
