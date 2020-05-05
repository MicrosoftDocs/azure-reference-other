---
title: Azure Monitor Logs reference - WVDHostRegistrations
description: Reference for WVDHostRegistrations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# WVDHostRegistrations

 Windows Virtual Desktop Host Registration Activity

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|CorrelationId|string|The activity Id.|
|_ResourceId|string||
|SessionHostIPAddress|string|The IP address of the session host that was registered with the WVD service.|
|SessionHostName|string|The name of the session host that was registered with the WVD service.|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the event.|
|Type|string||
