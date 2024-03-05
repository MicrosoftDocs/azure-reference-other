---
title: Azure Monitor tables for microsoft.dashboard/grafana
description: Azure Monitor tables for resource type microsoft.dashboard/grafana
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.dashboard/grafana  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AGSGrafanaLoginEvents](/azure/azure-monitor/reference/tables/AGSGrafanaLoginEvents)<p>Login events for an instance of Azure Managed Workspace for Grafana including user identity, user Grafana role (in success) and detailed message (in failure). | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/agsgrafanaloginevents)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|

