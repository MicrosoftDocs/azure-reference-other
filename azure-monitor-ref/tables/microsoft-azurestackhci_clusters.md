---
title: Azure Monitor tables for microsoft.azurestackhci/clusters
description: Azure Monitor tables for resource type microsoft.azurestackhci/clusters
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.azurestackhci/clusters  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [Event](/azure/azure-monitor/reference/tables/Event)<p>Events from Windows Event Log on Windows computers using the Log Analytics agent. | virtualmachines | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/event)|
| [Perf](/azure/azure-monitor/reference/tables/Perf)<p>Performance counters from Windows and Linux agents that provide insight into the performance of hardware components operating systems and applications. | virtualmachines, container | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/perf)|

