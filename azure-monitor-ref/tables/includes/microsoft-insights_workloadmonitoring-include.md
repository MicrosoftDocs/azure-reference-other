---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.insights/workloadmonitoring
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [InsightsMetrics](/azure/azure-monitor/reference/tables/InsightsMetrics)<p>Table that stores metrics. 'Perf' table also stores many metrics and over time they all will converge to InsightsMetrics for Azure Monitor Solutions  | virtualmachines, container, resources | AzureResources, ContainerInsights, InfrastructureInsights, LogManagement, ServiceMap, VMInsights | No| [Yes](/azure/azure-monitor/reference/queries/insightsmetrics)|

  
