---
title: Azure Monitor Logs reference - WVDErrors
description: Reference for WVDErrors table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# WVDErrors

 Windows Virtual Desktop Error Activity

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|ActivityType|string|The activity type for which the error happened.|
|Code|long|The error code for the error.|
|CodeSymbolic|string|The error code symbolic representation (if available).|
|CorrelationId|string|The activity Id.|
|Message|string|The error message.|
|_ResourceId|string||
|ServiceError|bool|Indicator whether this is a service or customer error.|
|Source|string|The source of the error.|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the event.|
|Type|string||
|UserName|string|The user for which the error happened.|
