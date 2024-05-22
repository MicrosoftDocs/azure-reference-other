---
ms.service: azure-monitor
ms.topic: include
ms.date: 05/22/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.operationalinsights/workspaces
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [LAQueryLogs](/azure/azure-monitor/reference/tables/LAQueryLogs)<p>Audit logs for queries executed in Log Analytics Workspaces. | audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/laquerylogs)|
| [LASummaryLogs](/azure/azure-monitor/reference/tables/LASummaryLogs)<p>Provides Summary logs rules execution details, including run status, duration and errors. Can be used to view bins executions statuses, identify rules that take a long time to complete, and failures that could be optimized in query, or shorted bin time. | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/lasummarylogs)|

  
