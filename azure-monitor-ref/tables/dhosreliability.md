---
title: Azure Monitor Logs reference - DHOSReliability
description: Reference for DHOSReliability table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/31/2023
---

# DHOSReliability

 

## Categories

- Desktop Analytics
## Solutions

- Device Health




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AbnormalShutdownCount | int |  |
| _BilledSize | real | The record size in bytes |
| Computer | string |  |
| ComputerID | string |  |
| ConfigMgrClientID | string |  |
| Country | string |  |
| DeviceLastSeenTime | datetime |  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| KernelModeCrashCount | int |  |
| KernelModeCrashFreePercentForIndustry | real |  |
| Manufacturer | string |  |
| Model | string |  |
| ModelFamily | string |  |
| OSArchitecture | string |  |
| OSBuildNumber | int |  |
| OSEdition | string |  |
| OSRevisionNumber | int |  |
| OSVersion | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
