---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.powerbi/tenants
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [PowerBIAuditTenant](/azure/azure-monitor/reference/tables/PowerBIAuditTenant)<p>Contains Power BI audit events as per the Activity Log and Office365 Audit Log. Covers operations over full lifecycle of Power BI assets such as creation, modification and deletion. | resources, audit | LogManagement | No| -|
| [PowerBIDatasetsTenant](/azure/azure-monitor/reference/tables/PowerBIDatasetsTenant)<p>Contains Analysis Services engine process events such as the start of a batch or transaction e.g. execute query, process partition. Typically used to monitor the performance, health and usage of Power BI's data engine. Contains information from the entire tenant. | resources | LogManagement | No| -|
| [PowerBIReportUsageTenant](/azure/azure-monitor/reference/tables/PowerBIReportUsageTenant)<p>Contains usage metric logs for open report and change report page for the workspaces on tenant level. Typically used to monitor usage of Power BI workspaces for customer tenant. | resources | LogManagement | No| -|

  
