---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.storage/storageaccounts
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [StorageBlobLogs](/azure/azure-monitor/reference/tables/StorageBlobLogs)<p>Storage Blob Service Logs Schema | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/storagebloblogs)|
| [StorageFileLogs](/azure/azure-monitor/reference/tables/StorageFileLogs)<p>Storage File Service Logs Schema | resources | LogManagement | Yes| -|
| [StorageQueueLogs](/azure/azure-monitor/reference/tables/StorageQueueLogs)<p>Storage Queue Service Logs Schema | resources | LogManagement | Yes| -|
| [StorageTableLogs](/azure/azure-monitor/reference/tables/StorageTableLogs)<p>Storage Table Service Logs Schema | resources | LogManagement | Yes| -|

  
