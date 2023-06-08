---
title: Azure Monitor Logs reference - AutoscaleScaleActionsLog
description: Reference for AutoscaleScaleActionsLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
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

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Category | string |  |
| CorrelationId | string |  |
| CreatedAsyncScaleActionJob | bool |  |
| CreatedAsyncScaleActionJobId | string |  |
| CurrentInstanceCount | int |  |
| _IsBillable | string |  |
| NewInstanceCount | int |  |
| OperationName | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceId | string |  |
| ResultDescription | string |  |
| ResultType | string |  |
| ScaleActionMessage | string |  |
| ScaleActionOperationId | string |  |
| ScaleActionOperationStatus | string |  |
| ScaleDirection | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetResourceId | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
