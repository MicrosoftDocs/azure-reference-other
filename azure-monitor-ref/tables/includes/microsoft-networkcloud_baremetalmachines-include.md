---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.networkcloud/baremetalmachines
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [NCBMBreakGlassAuditLogs](/azure/azure-monitor/reference/tables/NCBMBreakGlassAuditLogs)<p>Security log events on Nexus Baremetal Machines to monitor and detect user access to the system. | resources, security | LogManagement | Yes| -|
| [NCBMSecurityDefenderLogs](/azure/azure-monitor/reference/tables/NCBMSecurityDefenderLogs)<p>Security log events on Nexus Baremetal Machines to monitor and detect user access to the system. | resources, security | LogManagement | Yes| -|
| [NCBMSecurityLogs](/azure/azure-monitor/reference/tables/NCBMSecurityLogs)<p>Security log events on Nexus Baremetal Machines to monitor and detect user access to the system. | resources, security | LogManagement | Yes| -|
| [NCBMSystemLogs](/azure/azure-monitor/reference/tables/NCBMSystemLogs)<p>Syslog events on Nexus Baremetal Machines providing critical insights into system activities, errors and anomalies for effecient troubleshooting and monitoring. | resources | LogManagement | Yes| -|

  
