---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.storagecache/amlfilesytems
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AFSAuditLogs](/azure/azure-monitor/reference/tables/AFSAuditLogs)<p>This table contains audit logs retrieved from your Azure Managed Lustre filesystem resource. These logs capture all priviledged operations performed on each Azure Managed Lustre resource. They can be used to monitor events and configure alerts on your resource. | audit, resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/afsauditlogs)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

  
