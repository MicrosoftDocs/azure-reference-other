---
title: Azure Monitor Logs reference - MicrosoftDynamicsTelemetrySystemMetricsLogs
description: Reference for MicrosoftDynamicsTelemetrySystemMetricsLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
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
| Category | string | Log category |
| EnvironmentId | string | Unique identifier for an environment as shown in Lifecycle Services |
| EventName | string | Name of the event |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | Type of the machine (AOS/BI) emitting the events |
| RoleInstance | string | Name of the machine emitting the events |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the log. |
| Type | string | The name of the table |
