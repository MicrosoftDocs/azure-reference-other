---
title: Azure Monitor Logs reference - UAIESiteDiscovery
description: Reference for UAIESiteDiscovery table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# UAIESiteDiscovery

 

## Categories

- Desktop Analytics
## Solutions

- Upgrade Readiness




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActiveXGuid | string |  |
| ActiveXName | string |  |
| _BilledSize | real |  |
| BrowserStateReason | string |  |
| Computer | string |  |
| ComputerID | string |  |
| DocMode | string |  |
| DocModeReason | string |  |
| _IsBillable | string |  |
| IsRollup | bool |  |
| NumberOfVisits | int |  |
| SiteName | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| URL | string |  |
| Zone | string |  |
