---
title: Azure Monitor Logs reference - DHOSCrashData
description: Reference for DHOSCrashData table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/17/2023
---

# DHOSCrashData

 

## Categories

- Desktop Analytics
## Solutions

- Device Health




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real | The record size in bytes |
| Computer | string |  |
| ComputerID | string |  |
| DriverName | string |  |
| DriverVersion | string |  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| KernelModeCrashBugCheckCode | string |  |
| KernelModeCrashCount | int |  |
| KernelModeCrashFailureId | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
