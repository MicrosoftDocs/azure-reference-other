---
title: Azure Monitor Logs reference - AutoscaleScaleActionsLog
description: Reference for AutoscaleScaleActionsLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# AutoscaleScaleActionsLog

 

## Categories

- Azure Monitor
- Virtual Machines
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Monitor autoscale settings




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime||
|ResourceId|string||
|OperationName|string||
|Category|string||
|ResultType|string||
|ResultDescription|string||
|CorrelationId|string||
|TargetResourceId|string||
|CreatedAsyncScaleActionJob|bool||
|CreatedAsyncScaleActionJobId|string||
|CurrentInstanceCount|int||
|NewInstanceCount|int||
|ScaleActionMessage|string||
|ScaleActionOperationId|string||
|ScaleActionOperationStatus|string||
|ScaleDirection|string||
|Type|string||
