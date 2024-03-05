---
title: Azure Monitor tables for microsoft.insights/workloadmonitoring
description: Azure Monitor tables for resource type microsoft.insights/workloadmonitoring
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.insights/workloadmonitoring  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [InsightsMetrics](/azure/azure-monitor/reference/tables/InsightsMetrics)<p>Table that stores metrics. 'Perf' table also stores many metrics and over time they all will converge to InsightsMetrics for Azure Monitor Solutions  | virtualmachines, container, resources | AzureResources, ContainerInsights, InfrastructureInsights, LogManagement, ServiceMap, VMInsights | No| [Yes](/azure/azure-monitor/reference/queries/insightsmetrics)|

