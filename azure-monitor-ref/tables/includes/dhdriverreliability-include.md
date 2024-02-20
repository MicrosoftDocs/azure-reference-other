---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DHDriverReliability
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string |   |
| ComputerID | string |   |
| DeviceLastSeenTime | datetime |   |
| DriverKernelModeCrashCount | int |   |
| DriverName | string |   |
| DriverPercentCrashFreeDevicesForIndustry | real |   |
| DriverVendor | string |   |
| DriverVersion | string |   |
| HardwareType | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
