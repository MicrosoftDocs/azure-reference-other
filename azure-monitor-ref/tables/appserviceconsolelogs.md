---
title: Azure Monitor Logs reference - AppServiceConsoleLogs
description: Reference for AppServiceConsoleLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
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
|Category|string|Log category name|
|Host|string|Host where the application is running|
|Level|string|Verbosity level of log|
|_ResourceId|string||
|ResultDescription|string|Log message description|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|Time when event is generated|
|Type|string||
