---
title: Azure Monitor Logs reference - MAOfficeMacroHealth
description: Reference for MAOfficeMacroHealth table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# MAOfficeMacroHealth

 

## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime||
|OSVersion|string||
|OfficeAppRelease|string||
|OfficeMacroIssueId|string||
|DevicesWithOfficeApplicationInstalled|int||
|DevicesWithOfficeApplicationLoaded|int||
|RuntimeErrorsOnTarget|int||
|CompileErrorsOnTarget|int||
|DevicesWithAlertOnSource|int||
|DevicesWithAlertOnTarget|int||
|DevicesWithRuntimeErrorsOnSource|int||
|DevicesWithRuntimeErrorsOnTarget|int||
|DevicesWithRuntimeErrorsOnTargetPercentForCommercial|real||
|DevicesWithCompileErrorsOnSource|int||
|DevicesWithCompileErrorsOnTarget|int||
|DevicesWithCompileErrorsOnTargetPercentForCommercial|real||
|HealthStatus|string||
|Type|string||
