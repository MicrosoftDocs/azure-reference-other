---
title: Azure Monitor tables for microsoft.operationalinsights/workspaces
description: Azure Monitor tables for resource type microsoft.operationalinsights/workspaces
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.operationalinsights/workspaces  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureMetricsV2](/azure/azure-monitor/reference/tables/AzureMetricsV2)<p>Azure native platform metrics that can help to measure health and performance. AzureMetricsV2 includes metric categories and dimensions, improving upon legacy AzureMetrics table. | resources, monitor | LogManagement | Yes| -|
| [LAQueryLogs](/azure/azure-monitor/reference/tables/LAQueryLogs)<p>Audit logs for queries executed in Log Analytics Workspaces. | audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/laquerylogs)|
| [LASummaryLogs](/azure/azure-monitor/reference/tables/LASummaryLogs)<p>Provides Summary logs rules execution details, including run status, duration and errors. Can be used to view bins executions statuses, identify rules that take a long time to complete, and failures that could be optimized in query, or shorted bin time. | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/lasummarylogs)|

