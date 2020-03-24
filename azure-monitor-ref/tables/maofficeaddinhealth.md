---
title: Azure Monitor Logs reference - MAOfficeAddinHealth
description: Reference for MAOfficeAddinHealth table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# MAOfficeAddinHealth

 

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
|OfficeAppArchitecture|string||
|AddinInstanceId|string||
|ActiveDevicesOnTarget|int||
|ActiveDevicesOnSource|int||
|TotalSessionsOnTarget|int||
|TotalSessionsOnSource|int||
|TotalDevicesInstalledOnTarget|int||
|DevicesWithIncidentsOnSource|int||
|DevicesWithIncidentsOnTarget|int||
|DevicesWithIncidentsPercentOnTargetForCommercial|real||
|SessionsWithIncidentsOnSource|int||
|SessionsWithIncidentsOnTarget|int||
|SessionsWithIncidentsPercentOnTargetForCommercial|real||
|HealthStatus|string||
|Type|string||
