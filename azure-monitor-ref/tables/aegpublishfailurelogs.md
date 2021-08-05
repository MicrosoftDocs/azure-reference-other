---
title: Azure Monitor Logs reference - AegPublishFailureLogs
description: Reference for AegPublishFailureLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 8/5/2021
---

# AegPublishFailureLogs

 AEG Event publish failure logs

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Event Grid Domains




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|Log category name.|
|Message|string|Log message for the user.|
|OperationName|string|Name of the operation.|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string||
|SubResourceName|string|Name of the sub resource.|
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TenantId|string||
|Time|datetime|Time when log was generated.|
|TimeGenerated|datetime||
|Type|string|The name of the table|
