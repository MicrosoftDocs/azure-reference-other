---
title: Azure Monitor Logs reference - WorkloadDiagnosticLogs
description: Reference for WorkloadDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# WorkloadDiagnosticLogs

 Diagnostic logs from the Workload Monitoring data collection services running on the Monitoring VM. Includes logs from wli and ms-telegraf services. Used to troubleshoot configuration or data collection issues.

## Categories

- Workloads
- Azure Monitor
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Category | string | The category of the log. |
| Computer | string | Name of the Computer generating the log. |
| _IsBillable | string |  |
| Message | string | The message of the log entry. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| Status | string | The status of the record. Example: Error, Warning, etc. |
| Tags | dynamic | Dimensions or other metatata about the record. For example may contain the Monitoring profile ID the log entry is about. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp of when the log was generated. |
| Type | string | The name of the table |
