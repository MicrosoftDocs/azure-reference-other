---
title: Azure Monitor Logs reference - MAOfficeMacroGlobalHealth
description: Reference for MAOfficeMacroGlobalHealth table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 6/1/2021
---

# MAOfficeMacroGlobalHealth

[!INCLUDE [Note on Desktop Analytics table not intended for direct query](../../includes/azure-monitor-reference-ma-tables.md)]

## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

|Column|Type|Description|
|---|---|---|
|ActiveDevicesInLast14Days|int||
|CommercialDeviceCompileErrorDataSufficient|bool||
|CommercialDeviceCompileErrorRate|real||
|CommercialDeviceRuntimeErrorDataSufficient|bool||
|CommercialDeviceRuntimeErrorRate|real||
|NumberOfDevicesOnAppRelease|int||
|NumberOfDevicesOnPreviousAppReleases|int||
|OfficeAppRelease|string||
|OfficeMacroIssueId|string||
|SourceSystem|string||
|TimeGenerated|datetime||
|Type|string|The name of the table|
