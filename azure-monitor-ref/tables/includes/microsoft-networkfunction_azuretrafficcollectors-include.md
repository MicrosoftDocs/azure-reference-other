---
ms.service: azure-monitor
ms.topic: include
ms.date: 06/17/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.networkfunction/azuretrafficcollectors
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ATCExpressRouteCircuitIpfix](/azure/azure-monitor/reference/tables/ATCExpressRouteCircuitIpfix)<p>This table has Express Route Circuit IPFIX flow records. Flow records are captured and emitted by Azure Traffic Collector (ATC). | resources | LogManagement | No| -|
| [ATCPrivatePeeringMetadata](/azure/azure-monitor/reference/tables/ATCPrivatePeeringMetadata)<p>This table has Private Peering Vnet metadata. | resources | LogManagement | No| -|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

  
