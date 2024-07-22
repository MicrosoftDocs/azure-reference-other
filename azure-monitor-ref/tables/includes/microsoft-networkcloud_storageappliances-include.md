---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/22/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.networkcloud/storageappliances
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [NCSStorageAlerts](/azure/azure-monitor/reference/tables/NCSStorageAlerts)<p>Alert events logged from Nexus storage appliance providing storage system level alerts. | resources | LogManagement | Yes| -|
| [NCSStorageAudits](/azure/azure-monitor/reference/tables/NCSStorageAudits)<p>Audit log events from Nexus storage appliance providing insight into data and system access. | resources | LogManagement | Yes| -|
| [NCSStorageLogs](/azure/azure-monitor/reference/tables/NCSStorageLogs)<p>All Logs from Nexus storage appliance other than audit & alert logs. | resources | LogManagement | Yes| -|

  
