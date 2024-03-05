---
title: Azure Monitor tables for microsoft.timeseriesinsights/environments
description: Azure Monitor tables for resource type microsoft.timeseriesinsights/environments
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.timeseriesinsights/environments  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [TSIIngress](/azure/azure-monitor/reference/tables/TSIIngress)<p>The Ingress category tracks errors that occur in the ingress pipeline. This category includes errors that occur when receiving events (such as failures to connect to an Event Source) and processing events (such as errors when parsing an event payload). | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/tsiingress)|

