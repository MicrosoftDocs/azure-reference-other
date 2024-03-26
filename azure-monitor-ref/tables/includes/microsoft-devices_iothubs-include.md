---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.devices/iothubs
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [InsightsMetrics](/azure/azure-monitor/reference/tables/InsightsMetrics)<p>Table that stores metrics. 'Perf' table also stores many metrics and over time they all will converge to InsightsMetrics for Azure Monitor Solutions  | virtualmachines, container, resources | AzureResources, ContainerInsights, InfrastructureInsights, LogManagement, ServiceMap, VMInsights | No| [Yes](/azure/azure-monitor/reference/queries/insightsmetrics)|
| [IoTHubDistributedTracing](/azure/azure-monitor/reference/tables/IoTHubDistributedTracing)<p>The distributed tracing category tracks the trace-id and span-id for messages that carry the trace context header. To fully enable these logs, client-side code must be updated by following https://aka.ms/iottracing | resources | LogManagement | No| -|

  
