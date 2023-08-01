---
title: Azure Monitor Logs reference - DHDriverReliability
description: Reference for DHDriverReliability table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/31/2023
---

# DHDriverReliability

 

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
| DeviceLastSeenTime | datetime |  |
| DriverKernelModeCrashCount | int |  |
| DriverName | string |  |
| DriverPercentCrashFreeDevicesForIndustry | real |  |
| DriverVendor | string |  |
| DriverVersion | string |  |
| HardwareType | string |  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
