---
title: Azure Monitor tables for microsoft.d365customerinsights/instances
description: Azure Monitor tables for resource type microsoft.d365customerinsights/instances
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.d365customerinsights/instances  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [CIEventsAudit](/azure/azure-monitor/reference/tables/CIEventsAudit)<p>All API requests in the context of the Customer Insights instance, for example all user actions while configuring and using the instance. POST|PUT|DELETE|PATCH operations go into this category. | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/cieventsaudit)|
| [CIEventsOperational](/azure/azure-monitor/reference/tables/CIEventsOperational)<p>Events generated using the service, for example GET requests or the execution events of a workflow. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/cieventsoperational)|

