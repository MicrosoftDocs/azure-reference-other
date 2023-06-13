---
title: Azure Monitor Logs reference - MicrosoftDynamicsTelemetrySystemMetricsLogs
description: Reference for MicrosoftDynamicsTelemetrySystemMetricsLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# MicrosoftDynamicsTelemetrySystemMetricsLogs

 Microsoft Dynamics Telemetry System Metrics Logs

## Categories

- Workloads
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Category | string | Log category |
| EnvironmentId | string | Unique identifier for an environment as shown in Lifecycle Services |
| EventName | string | Name of the event |
| _IsBillable | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | Type of the machine (AOS/BI) emitting the events |
| RoleInstance | string | Name of the machine emitting the events |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the log. |
| Type | string | The name of the table |
