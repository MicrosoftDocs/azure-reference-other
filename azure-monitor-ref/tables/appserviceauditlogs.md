---
title: Azure Monitor Logs reference - AppServiceAuditLogs
description: Reference for AppServiceAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# AppServiceAuditLogs

 Logs generated when publishing users successfully log on via one of the App Service publishing protocols.

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|Time when event is generated|
|Category|string|Log category name|
|OperationName|string|Name of the operation|
|User|string|Username used for publishing access|
|UserDisplayName|string|Email address of a user in case publishing was authorized via AAD authentication|
|UserAddress|string|Client IP addres of the publishing user|
|Protocol|string|Authentication protocol|
|Type|string||
|_ResourceId|string||
