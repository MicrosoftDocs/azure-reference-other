---
title: Azure Monitor Logs reference - AppServicePlatformLogs
description: Reference for AppServicePlatformLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/29/2021
---

# AppServicePlatformLogs

 Logs generated through AppService platform for your application.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- App Services




## Columns

|Column|Type|Description|
|---|---|---|
|ContainerId|string|Application container id|
|Host|string|Host where the application is running|
|Level|string|Level of log verbosity|
|Message|string|Log message|
|OperationName|string|The name of the operation represented by this event.|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string||
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TenantId|string||
|TimeGenerated|datetime|Time when event is generated|
|Type|string|The name of the table|
