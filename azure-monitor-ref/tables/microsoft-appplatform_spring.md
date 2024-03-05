---
title: Azure Monitor tables for microsoft.appplatform/spring
description: Azure Monitor tables for resource type microsoft.appplatform/spring
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.appplatform/spring  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AppPlatformBuildLogs](/azure/azure-monitor/reference/tables/AppPlatformBuildLogs)<p>Azure Spring Cloud build logs of user source codes. | undefined | LogManagement | No| -|
| [AppPlatformContainerEventLogs](/azure/azure-monitor/reference/tables/AppPlatformContainerEventLogs)<p>Azure Spring Cloud container event logs of user applications. | resources | LogManagement | No| -|
| [AppPlatformIngressLogs](/azure/azure-monitor/reference/tables/AppPlatformIngressLogs)<p>Azure Spring Cloud ingress logs, currently it is nginx access logs. | resources | LogManagement | No| -|
| [AppPlatformLogsforSpring](/azure/azure-monitor/reference/tables/AppPlatformLogsforSpring)<p>App Platform Logs for Spring. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/appplatformlogsforspring)|
| [AppPlatformSystemLogs](/azure/azure-monitor/reference/tables/AppPlatformSystemLogs)<p>Azure Spring Cloud System Logs. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/appplatformsystemlogs)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

