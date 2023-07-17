---
title: Azure Monitor Logs reference - AEWAuditLogs
description: Reference for AEWAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/17/2023
---

# AEWAuditLogs

 Audit, activity and status for the Experiment Workspace.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Experiment Workspace




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActionName | string | The event name. |
| _BilledSize | real | The record size in bytes |
| Category | string | The event category. Typical log categories are Audit, Operational, Execution, and Request. |
| ExpComponentName | string | The Exp component sending the log. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| Message | string | The message in the log. |
| Operator | string | The user identity triggering the event. |
| RequestUri | string | The event URI. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) of the HTTP request. |
| Type | string | The name of the table |
