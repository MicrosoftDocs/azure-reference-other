---
title: Azure Monitor tables for microsoft.eventgrid/domains
description: Azure Monitor tables for resource type microsoft.eventgrid/domains
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.eventgrid/domains  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AegDataPlaneRequests](/azure/azure-monitor/reference/tables/AegDataPlaneRequests)<p>Logs for Event Grid data plane requests (publish and options) against a topic/domain/partnernamespace. It can be used for auditing purposes. Logs are aggregated over a minute and displays the total number of requests with specific request properties. | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aegdataplanerequests)|
| [AegDeliveryFailureLogs](/azure/azure-monitor/reference/tables/AegDeliveryFailureLogs)<p>Azure Event Grid - event delivery failure logs. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aegdeliveryfailurelogs)|
| [AegPublishFailureLogs](/azure/azure-monitor/reference/tables/AegPublishFailureLogs)<p>Azure Event Grid - event publish failure logs. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aegpublishfailurelogs)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

