---
title: Azure Monitor Logs reference - AmlRunEvent
description: Reference for AmlRunEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# AmlRunEvent

 Events when ML experiments are accessed (read, created, or deleted).

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Machine Learning




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AadTenantId | string | The AAD tenant ID the operation was submitted for. |
| AmlWorkspaceId | string | The unique ID of the workspace. |
| Identity | dynamic | The identity of the user or application that performed the operation. |
| OperationName | string | The name of the operation associated with the log entry. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RunId | string | The unique ID of the run. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
