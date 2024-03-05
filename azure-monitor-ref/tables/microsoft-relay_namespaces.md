---
title: Azure Monitor tables for microsoft.relay/namespaces
description: Azure Monitor tables for resource type microsoft.relay/namespaces
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.relay/namespaces  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AZMSHybridConnectionsEvents](/azure/azure-monitor/reference/tables/AZMSHybridConnectionsEvents)<p>Captures all hybrid connection events that are performed on the Azure Relay namespace. | resources, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/azmshybridconnectionsevents)|
| [AZMSVnetConnectionEvents](/azure/azure-monitor/reference/tables/AZMSVnetConnectionEvents)<p>Captures all virtual network and IP filtering logs for Azure Event Hubs and Azure Service Bus. These would only be emitted if namespace allows access from selected networks or from specific IP address (IP Filter rules). | resources, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/azmsvnetconnectionevents)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

