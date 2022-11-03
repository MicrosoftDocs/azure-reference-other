---
title: Azure Monitor Logs reference - AppServiceFileAuditLogs
description: Reference for AppServiceFileAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# AppServiceFileAuditLogs

 Logs generated when app service content is modified.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- App Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | Log category name |
| OperationName | string | Operation performed on a file |
| Path | string | Path to the file that was changed |
| Process | string | Type of the process that change the file |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time when event is generated |
| Type | string | The name of the table |
