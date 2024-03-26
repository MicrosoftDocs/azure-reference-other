---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.insights/autoscalesettings
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AutoscaleEvaluationsLog](/azure/azure-monitor/reference/tables/AutoscaleEvaluationsLog)<p> | monitor, virtualmachines, resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/autoscaleevaluationslog)|
| [AutoscaleScaleActionsLog](/azure/azure-monitor/reference/tables/AutoscaleScaleActionsLog)<p> | monitor, virtualmachines, resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/autoscalescaleactionslog)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

  
