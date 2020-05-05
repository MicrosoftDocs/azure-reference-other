---
title: Azure Monitor Logs reference - WVDManagement
description: Reference for WVDManagement table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# WVDManagement

 Windows Virtual Desktop Management Activity

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|CorrelationId|string|The activity Id.|
|ObjectsCreated|int|The number of objects that were created.|
|ObjectsDeleted|int|The number of objects that were deleted.|
|ObjectsFetched|int|The number of objects that were fetched.|
|ObjectsUpdated|int|The number of objects that were updated.|
|_ResourceId|string||
|Route|string|The route for the management request.|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the event.|
|Type|string||
|UserName|string|The user that initiated the management request.|
