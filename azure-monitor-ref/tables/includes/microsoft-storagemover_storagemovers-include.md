---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.storagemover/storagemovers
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [StorageMoverCopyLogsFailed](/azure/azure-monitor/reference/tables/StorageMoverCopyLogsFailed)<p>The result logs generated during the execution of Storage Mover job runs where the transfer result is 'Failed'. The logs include the details of the scanned items and their transfer result. | resources | LogManagement | Yes| -|
| [StorageMoverCopyLogsTransferred](/azure/azure-monitor/reference/tables/StorageMoverCopyLogsTransferred)<p>The result logs generated during the execution of Storage Mover job runs where the transfer result is 'Transferred'. The logs include the details of the scanned items and their transfer result. | resources | LogManagement | Yes| -|
| [StorageMoverJobRunLogs](/azure/azure-monitor/reference/tables/StorageMoverJobRunLogs)<p>Logs associated with Storage Mover job runs. | resources | LogManagement | Yes| -|

  
