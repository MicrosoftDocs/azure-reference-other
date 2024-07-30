---
title: Azure Monitor Logs reference - WorkloadDiagnosticLogs
description: Reference for WorkloadDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# WorkloadDiagnosticLogs

Diagnostic logs from the Workload Monitoring data collection services running on the Monitoring VM. Includes logs from wli and ms-telegraf services. Used to troubleshoot configuration or data collection issues.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|-|
|**Categories**|Workloads, Azure Monitor|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/workloaddiagnosticlogs)|



## Columns
  
[!INCLUDE [workloaddiagnosticlogs](./includes/workloaddiagnosticlogs-include.md)]
