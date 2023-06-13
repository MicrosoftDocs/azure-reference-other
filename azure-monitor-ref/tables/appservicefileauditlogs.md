---
title: Azure Monitor Logs reference - AppServiceFileAuditLogs
description: Reference for AppServiceFileAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
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
| _BilledSize | real |  |
| Category | string | Log category name |
| _IsBillable | string |  |
| OperationName | string | Operation performed on a file |
| Path | string | Path to the file that was changed |
| Process | string | Type of the process that change the file |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time when event is generated |
| Type | string | The name of the table |
