---
title: Azure Monitor Logs reference - UCClientReadinessStatus
description: Reference for UCClientReadinessStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# UCClientReadinessStatus

 Update Compliance - Status message for an UC client device, which indicates update readiness of the given device for a specific target version.

## Solutions

- LogManagement
- Update Compliance




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AzureADDeviceId | string | A GUID corresponding to the AAD tenant to which the device belongs. |
| AzureADTenantId | string | A GUID corresponding to this device's AAD device ID. |
| DeviceName | string | The Device given name. |
| GlobalDeviceId | string | Microsoft internal global device identifier. |
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
| SourceSystem | string |  |
| TargetOSBuild | string | The currently-installed Windows 10 Build in the format 'Major'.'Revision'. 'Major' corresponds to which Feature Update the device is on, whereas 'Revision' corresponds to which quality update the device is on. Mappings between Feature release and Major, as well as Revision and KBs, are available aka.ms/win10releaseinfo. |
| TargetOSName | string | The version of Windows 10 as is organized on aka.ms/win10releaseinfo. |
| TargetOSVersion | string | The version of Windows 10 as is organized on aka.ms/win10releaseinfo. |
| TenantId | string |  |
| TimeGenerated | datetime | Time at which this event is generated. |
| Type | string | The name of the table |
