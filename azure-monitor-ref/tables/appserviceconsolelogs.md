---
title: Azure Monitor Logs reference - AppServiceConsoleLogs
description: Reference for AppServiceConsoleLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# AppServiceConsoleLogs

 Console logs generated from application or container.

## Categories

- Azure Resources
- Applications
## Solutions

- LogManagement
## Resource types

- App Service




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|Time when event is generated|
|Category|string|Log category name|
|Level|string|Verbosity level of log|
|Host|string|Host where the application is running|
|ResultDescription|string|Log message description|
|Type|string||
|_ResourceId|string||
