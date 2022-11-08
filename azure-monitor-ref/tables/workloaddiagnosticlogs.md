---
title: Azure Monitor Logs reference - WorkloadDiagnosticLogs
description: Reference for WorkloadDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
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
| Category | string | The category of the log. |
| Computer | string | Name of the Computer generating the log. |
| Message | string | The message of the log entry. |
| SourceSystem | string |  |
| Status | string | The status of the record. Example: Error, Warning, etc. |
| Tags | dynamic | Dimensions or other metatata about the record. For example may contain the Monitoring profile ID the log entry is about. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp of when the log was generated. |
| Type | string | The name of the table |
