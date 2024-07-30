---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: DHOSCrashData
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string |   |
| ComputerID | string |   |
| DriverName | string |   |
| DriverVersion | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| KernelModeCrashBugCheckCode | string |   |
| KernelModeCrashCount | int |   |
| KernelModeCrashFailureId | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
