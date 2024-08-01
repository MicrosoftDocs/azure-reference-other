---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: MADevice
---


| Column | Type | Description |
|---|---|---|
| AbnormalShutdownCount | int |   |
| AbnormalShutdownCountTrailing | int |   |
| AssignedToDeploymentPlan | bool |   |
| _BilledSize | real | The record size in bytes |
| BiosVersion | string |   |
| ConfigMgrClientID | string |   |
| DeviceAge | int |   |
| DeviceId | string |   |
| DeviceLastSeenDate | datetime |   |
| DeviceName | string |   |
| DiskFreeSpace | int |   |
| InventoryCompleteness | bool |   |
| InventoryVersion | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| KernelModeCrashCount | int |   |
| KernelModeCrashCountTrailing | int |   |
| KernelModeCrashFreePercentTrailingIndustry | real |   |
| Manufacturer | string |   |
| Model | string |   |
| ModelFamily | string |   |
| OEMSerialNumber | string |   |
| OfficeAudienceFFN | string |   |
| OfficeAudiencesGroup | string |   |
| OfficeBuild | string |   |
| OfficeChannel | string |   |
| OfficeVersion | string |   |
| OSArchitecture | string |   |
| OSBuild | string |   |
| OSBuildNumber | int |   |
| OSEdition | string |   |
| OSFamily | string |   |
| OSRevisionNumber | int |   |
| OSServicingBranch | string |   |
| OSVersion | string |   |
| Processor | string |   |
| Region | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TimeGenerated | datetime |   |
| TotalDiskSize | int |   |
| TotalRAM | real |   |
| Type | string | The name of the table |
| WindowsTelemetryLevel | int |   |
