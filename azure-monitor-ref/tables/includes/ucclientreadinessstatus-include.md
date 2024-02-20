---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: UCClientReadinessStatus
---


| Column | Type | Description |
|---|---|---|
| AzureADDeviceId | string | A GUID corresponding to the AAD tenant to which the device belongs. |
| AzureADTenantId | string | A GUID corresponding to this device's AAD device ID. |
| _BilledSize | real | The record size in bytes |
| DeviceName | string | The Device given name. |
| GlobalDeviceId | string | Microsoft internal global device identifier. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OSBuild | string | The currently-installed Windows 10 Build in the format 'Major'.'Revision'. 'Major' corresponds to which Feature Update the device is on, whereas 'Revision' corresponds to which quality update the device is on. Mappings between Feature release and Major, as well as Revision and KBs, are available aka.ms/win10releaseinfo. |
| OSName | string | The version of Windows 10 as is organized on aka.ms/win10releaseinfo. |
| OSVersion | string | The version of Windows 10 as is organized on aka.ms/win10releaseinfo. |
| ReadinessExpiryTime | datetime | The time the readiness report expires. |
| ReadinessReason | string | Reason why the device is not capable of taking target OS and version. |
| ReadinessScanTime | datetime | The time the readiness generated this specific record. |
| ReadinessStatus | string | Whether or not the device is capable of taking target OS and version. |
| SCCMClientId | string | A GUID corresponding to the SCCM client ID on the device. |
| SetupReadinessExpiryTime | datetime | The time the readiness report expires. |
| SetupReadinessReason | string | Reason why the device is not capable of taking target OS and version when setup ran. |
| SetupReadinessStatus | string | Whether or not the device is capable of taking target OS and version when setup ran. |
| SetupReadinessTime | datetime | The time the readiness generated this specific record when setup ran. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TargetOSBuild | string | The currently-installed Windows 10 Build in the format 'Major'.'Revision'. 'Major' corresponds to which Feature Update the device is on, whereas 'Revision' corresponds to which quality update the device is on. Mappings between Feature release and Major, as well as Revision and KBs, are available aka.ms/win10releaseinfo. |
| TargetOSName | string | The version of Windows 10 as is organized on aka.ms/win10releaseinfo. |
| TargetOSVersion | string | The version of Windows 10 as is organized on aka.ms/win10releaseinfo. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time at which this event is generated. |
| Type | string | The name of the table |
