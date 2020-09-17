---
title: Azure Monitor Logs reference - AppServiceIPSecAuditLogs
description: Reference for AppServiceIPSecAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# AppServiceIPSecAuditLogs

 Logs generated through your application which will show requests made to your web app if there were any IP access restriction rules created.

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|The name of the operation of this event|
|CIp|string|IP address of the client|
|CsHost|string|Host header of the HTTP request|
|Details|string|Additional information|
|OperationName|string|The name of the operation of this event|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|Result|string|The result whether the access is Allowed or Denied|
|ServiceEndpoint|string|This indicates whether the access is via Virtual Network Service Endpoint communication|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|Time (UTC) of the HTTP Request|
|Type|string|The name of the table|
|XAzureFDID|string|X-Azure-FDID header (Azure Frontdoor Id) of the HTTP request|
|XFDHealthProbe|string|X-FD-HealthProbe (Azure Frontdoor Health Probe) of the HTTP request|
|XForwardedFor|string|X-Forwarded-For header of the HTTP request|
|XForwardedHost|string|X-Forwarded-Host header of the HTTP request|
