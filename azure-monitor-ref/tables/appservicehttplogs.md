---
title: Azure Monitor Logs reference - AppServiceHTTPLogs
description: Reference for AppServiceHTTPLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
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
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|Time when event is generated|
|Category|string|Log category name|
|CsMethod|string|HTTP Verb on request|
|CsUriStem|string|HTTP Target on request|
|SPort|string|Server port number|
|CIp|string|IP address of the client|
|UserAgent|string|User Agent on HTTP request|
|CsHost|string|Host name header on HTTP request|
|ScStatus|int|HTTP Status Code|
|ScSubStatus|string|Substatus error code on HTTP request|
|ScWin32Status|string|Windows status code on HTTP request|
|ScBytes|int|Number of bytes sent by server|
|CsBytes|int|Number of bytes received by server|
|TimeTaken|int|Time taken by HTTP request|
|Result|string||
|Type|string||
|_ResourceId|string||
