---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.datashare/accounts
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [MicrosoftDataShareReceivedSnapshotLog](/azure/azure-monitor/reference/tables/MicrosoftDataShareReceivedSnapshotLog)<p>Data Share consumer side synchronization logs. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/microsoftdatasharereceivedsnapshotlog)|
| [MicrosoftDataShareSentSnapshotLog](/azure/azure-monitor/reference/tables/MicrosoftDataShareSentSnapshotLog)<p>Data Share provider side synchronization logs. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/microsoftdatasharesentsnapshotlog)|

  
