---
title: Azure Monitor tables for microsoft.automation/automationaccounts
description: Azure Monitor tables for resource type microsoft.automation/automationaccounts
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.automation/automationaccounts  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [Heartbeat](/azure/azure-monitor/reference/tables/Heartbeat)<p>Records logged by Log Analytics agents once per minute to report on agent health. | virtualmachines, container, management | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/heartbeat)|
| [Update](/azure/azure-monitor/reference/tables/Update)<p>Details for update schedule run. Includes information such as which updates where available and which were installed. | management, security | Security, SecurityCenter, SecurityCenterFree, Updates | No| [Yes](/azure/azure-monitor/reference/queries/update)|
| [UpdateRunProgress](/azure/azure-monitor/reference/tables/UpdateRunProgress)<p>Breaks down each run of your update schedule by the patches available at the time with details on the installation status of each patch. | management | Updates | No| [Yes](/azure/azure-monitor/reference/queries/updaterunprogress)|
| [UpdateSummary](/azure/azure-monitor/reference/tables/UpdateSummary)<p>Summary for each update schedule run. Includes information such as how many updates were not installed. | virtualmachines | Security, SecurityCenter, SecurityCenterFree, Updates | No| [Yes](/azure/azure-monitor/reference/queries/updatesummary)|

