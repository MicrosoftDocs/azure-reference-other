---
title: Azure Monitor Logs reference - AppServiceConsoleLogs
description: Reference for AppServiceConsoleLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AppServiceConsoleLogs

 Console logs generated from application or container.

## Categories

- Azure Resources
- Applications
## Solutions

- LogManagement
## Resource types

- App Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Category | string | Log category name |
| ContainerId | string | Application container id |
| Host | string | Host where the application is running |
| _IsBillable | string |  |
| Level | string | Verbosity level of log |
| OperationName | string | The name of the operation represented by this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Log message description |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time when event is generated |
| Type | string | The name of the table |
