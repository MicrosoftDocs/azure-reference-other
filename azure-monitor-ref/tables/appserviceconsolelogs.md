---
title: Azure Monitor Logs reference - AppServiceConsoleLogs
description: Reference for AppServiceConsoleLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
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
| ContainerId | string | Application container id |
| Host | string | Host where the application is running |
| Level | string | Verbosity level of log |
| OperationName | string | The name of the operation represented by this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Log message description |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time when event is generated |
| Type | string | The name of the table |
