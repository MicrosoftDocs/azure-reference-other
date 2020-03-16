---
title: Azure Monitor Logs reference - UpdateRunProgress
description: Reference for UpdateRunProgress table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# UpdateRunProgress

 Breaks down each run of your update schedule by the patches available at the time with details on the installation status of each patch.

## Categories

- IT & Management Tools
## Solutions

- Update Management
## Resource types

- Virtual machine
- Virtual machine scale set




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime||
|ManagementGroupName|string||
|SourceComputerId|string||
|KBID|string||
|UpdateId|string||
|SucceededOnRetry|bool||
|ErrorResult|string||
|UpdateRunName|string||
|InstallationStatus|string||
|Computer|string||
|Title|string||
|Product|string||
|OSType|string||
|StartTime|datetime||
|EndTime|datetime||
|CorrelationId|string||
|SubscriptionId|string||
|ResourceGroup|string||
|ResourceProvider|string||
|Resource|string||
|ResourceId|string||
|ResourceType|string||
|ComputerEnvironment|string||
|VMUUID|string||
|Type|string||
|_ResourceId|string||
