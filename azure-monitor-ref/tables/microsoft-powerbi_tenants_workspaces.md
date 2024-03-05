---
title: Azure Monitor tables for microsoft.powerbi/tenants/workspaces
description: Azure Monitor tables for resource type microsoft.powerbi/tenants/workspaces
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.powerbi/tenants/workspaces  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [PowerBIDatasetsWorkspace](/azure/azure-monitor/reference/tables/PowerBIDatasetsWorkspace)<p>Contains Analysis Services engine process events such as the start of a batch or transaction e.g. execute query, process partition. Typically used to monitor the performance, health and usage of Power BI's data engine. Contains information from the entire tenant. | resources | LogManagement | No| -|
| [PowerBIReportUsageWorkspace](/azure/azure-monitor/reference/tables/PowerBIReportUsageWorkspace)<p>Contains usage metric logs for open report and change report page of Power BI on workspace level. Typically used to monitor Power BI workspace usage for customer workspace. | resources | LogManagement | No| -|

