---
title: Azure Monitor Logs reference - AppServiceHTTPLogs
description: Reference for AppServiceHTTPLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# AppServiceHTTPLogs

 Logs generated through your application and pushed to Azure Monitoring.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- App Service




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|Log category name|
|CIp|string|IP address of the client|
|CsBytes|int|Number of bytes received by server|
|CsHost|string|Host name header on HTTP request|
|CsMethod|string|HTTP Verb on request|
|CsUriStem|string|HTTP Target on request|
|_ResourceId|string||
|Result|string||
|ScBytes|int|Number of bytes sent by server|
|ScStatus|int|HTTP Status Code|
|ScSubStatus|string|Substatus error code on HTTP request|
|ScWin32Status|string|Windows status code on HTTP request|
|SourceSystem|string||
|SPort|string|Server port number|
|TenantId|string||
|TimeGenerated|datetime|Time when event is generated|
|TimeTaken|int|Time taken by HTTP request|
|Type|string||
|UserAgent|string|User Agent on HTTP request|
