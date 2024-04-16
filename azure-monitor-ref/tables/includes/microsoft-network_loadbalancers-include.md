---
ms.service: azure-monitor
ms.topic: include
ms.date: 04/15/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.network/loadbalancers
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ALBHealthEvent](/azure/azure-monitor/reference/tables/ALBHealthEvent)<p>Table of events related to the availability and health of a load balancer resource. | resources, monitor | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/albhealthevent)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|

  
