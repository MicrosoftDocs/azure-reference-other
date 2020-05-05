---
title: Azure Monitor Logs reference - UpdateRunProgress
description: Reference for UpdateRunProgress table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
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
|Computer|string||
|ComputerEnvironment|string||
|CorrelationId|string||
|EndTime|datetime||
|ErrorResult|string||
|InstallationStatus|string||
|KBID|string||
|ManagementGroupName|string||
|OSType|string||
|Product|string||
|Resource|string||
|ResourceGroup|string||
|ResourceId|string||
|_ResourceId|string||
|ResourceProvider|string||
|ResourceType|string||
|SourceComputerId|string||
|SourceSystem|string||
|StartTime|datetime||
|SubscriptionId|string||
|SucceededOnRetry|bool||
|TimeGenerated|datetime||
|Title|string||
|Type|string||
|UpdateId|string||
|UpdateRunName|string||
|VMUUID|string||
