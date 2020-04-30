---
title: Azure Monitor Logs reference - WVDCheckpoints
description: Reference for WVDCheckpoints table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# WVDCheckpoints

 Windows Virtual Desktop Checkpoint Activity

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|ActivityType|string|The type of activity for which this checkpoint was reported.|
|CorrelationId|string|The correlation Id for the activity.|
|Name|string|The name of the checkpoint.|
|Parameters|dynamic|The parameters for the checkpoint.|
|_ResourceId|string||
|Source|string|The component that emitted the checkpoint.|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the event.|
|Type|string||
|UserName|string|The user name for the activity associated with the checkpoint.|
