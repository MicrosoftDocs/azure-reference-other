---
title: Azure Monitor Logs reference - MAOfficeAppHealth
description: Reference for MAOfficeAppHealth table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# MAOfficeAppHealth

 

## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime||
|OfficeAppId|string||
|OfficeAppName|string||
|OfficeAppMajorVersion|int||
|OfficeAppRelease|string||
|OfficeAppArchitecture|string||
|DevicesWithCrashes|int||
|DevicesWithCrashesPercentForCommercial|real||
|SessionsWithCrashes|int||
|SessionsWithCrashesPercentForCommercial|real||
|ActiveDevices|int||
|TotalDevicesInstalled|int||
|TotalSessions|int||
|HealthStatus|string||
|SessionHealthStatus|string||
|DeviceHealthStatus|string||
|RiskAssessment|string||
|Issue|string||
|Type|string||
