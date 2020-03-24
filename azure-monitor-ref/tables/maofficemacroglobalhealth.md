---
title: Azure Monitor Logs reference - MAOfficeMacroGlobalHealth
description: Reference for MAOfficeMacroGlobalHealth table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# MAOfficeMacroGlobalHealth

 

## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime||
|OfficeAppRelease|string||
|OfficeMacroIssueId|string||
|CommercialDeviceRuntimeErrorRate|real||
|CommercialDeviceCompileErrorRate|real||
|CommercialDeviceRuntimeErrorDataSufficient|bool||
|CommercialDeviceCompileErrorDataSufficient|bool||
|NumberOfDevicesOnAppRelease|int||
|NumberOfDevicesOnPreviousAppReleases|int||
|ActiveDevicesInLast14Days|int||
|Type|string||
