---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/02/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.cache/redis
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ACRConnectedClientList](/azure/azure-monitor/reference/tables/ACRConnectedClientList)<p>Logs count of Redis clients connected to a cache instance and their IP addresses, logged at a 10-second interval. | resources, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/acrconnectedclientlist)|
| [ACREntraAuthenticationAuditLog](/azure/azure-monitor/reference/tables/ACREntraAuthenticationAuditLog)<p>Logs Microsoft Entra authentication audit events for Azure Cache for Redis. | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/acrentraauthenticationauditlog)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

  
