---
title: Azure Monitor tables for microsoft.network/applicationgateways
description: Azure Monitor tables for resource type microsoft.network/applicationgateways
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.network/applicationgateways  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AGWAccessLogs](/azure/azure-monitor/reference/tables/AGWAccessLogs)<p>Contains all the log to view Application Gateway access patterns and analyze important information. This includes the caller's IP, requested URL, response latency, return code, and bytes in and out. | resources, network, audit | LogManagement | Yes| -|
| [AGWFirewallLogs](/azure/azure-monitor/reference/tables/AGWFirewallLogs)<p>Contains all the logs to view the requests that are logged through either detection or prevention mode of an application gateway that is configured with the web application firewall. | resources, network, audit | LogManagement | Yes| -|
| [AGWPerformanceLogs](/azure/azure-monitor/reference/tables/AGWPerformanceLogs)<p>Contains all the logs to view how Application Gateway instances are performing. This log captures performance information for each instance, including total requests served, throughput in bytes, total requests served, failed request count, and healthy and unhealthy backend instance count.The Performance log is available only for the v1 SKU. | resources, network, audit | LogManagement | Yes| -|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

