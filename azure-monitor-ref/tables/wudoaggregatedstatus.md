---
title: Azure Monitor Logs reference - WUDOAggregatedStatus
description: Reference for WUDOAggregatedStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# WUDOAggregatedStatus

 

## Categories

- Desktop Analytics
## Solutions

- Update Compliance




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| BWOptPercent28Days | real |  |
| BytesFromCDN | long |  |
| BytesFromGroupPeers | long |  |
| BytesFromIntPeers | long |  |
| BytesFromPeers | long |  |
| ContentType | string |  |
| DeviceCount | int |  |
| DownloadMode | string |  |
| _IsBillable | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
