---
title: Azure Monitor Logs reference - AppServiceHTTPLogs
description: Reference for AppServiceHTTPLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 6/1/2021
---

# AppServiceHTTPLogs

 Logs generated through your application and pushed to Azure Monitoring.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- App Services




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|Log category name|
|CIp|string|IP address of the client|
|Cookie|string|Cookie on HTTP request|
|CsBytes|int|Number of bytes received by server|
|CsHost|string|Host name header on HTTP request|
|CsMethod|string|HTTP verb on request|
|CsUriQuery|string|URI query on HTTP request|
|CsUriStem|string|HTTP target on request|
|CsUsername|string|The name of the authenticated user on HTTP request|
|Referer|string|The site that the user last visited. This site provided a link to the current site|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|Result|string|Success / Failure of HTTP request|
|ScBytes|int|Number of bytes sent by server|
|ScStatus|int|HTTP status code|
|ScSubStatus|string|Substatus error code on HTTP request|
|ScWin32Status|string|Windows status code on HTTP request|
|SourceSystem|string||
|SPort|string|Server port number|
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TenantId|string||
|TimeGenerated|datetime|Time when event is generated|
|TimeTaken|int|Time taken by HTTP request in milliseconds|
|Type|string|The name of the table|
|UserAgent|string|User agent on HTTP request|
