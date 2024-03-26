---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.insights/components
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AppAvailabilityResults](/azure/azure-monitor/reference/tables/AppAvailabilityResults)<p>Application Insights availability test results. | applications | LogManagement | No| -|
| [AppBrowserTimings](/azure/azure-monitor/reference/tables/AppBrowserTimings)<p>Application Insights browser timings. | applications | LogManagement | No| -|
| [AppDependencies](/azure/azure-monitor/reference/tables/AppDependencies)<p>Application Insights dependencies. | applications | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/appdependencies)|
| [AppEvents](/azure/azure-monitor/reference/tables/AppEvents)<p>Application Insights events. | applications | LogManagement | No| -|
| [AppExceptions](/azure/azure-monitor/reference/tables/AppExceptions)<p>Application Insights exceptions. | applications | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/appexceptions)|
| [AppMetrics](/azure/azure-monitor/reference/tables/AppMetrics)<p>Application Insights metrics. | applications | LogManagement | No| -|
| [AppPageViews](/azure/azure-monitor/reference/tables/AppPageViews)<p>Application Insights page views. | applications | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/apppageviews)|
| [AppPerformanceCounters](/azure/azure-monitor/reference/tables/AppPerformanceCounters)<p>Application Insights performance counters. | applications | LogManagement | No| -|
| [AppRequests](/azure/azure-monitor/reference/tables/AppRequests)<p>Application Insights requests. | applications | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/apprequests)|
| [AppSystemEvents](/azure/azure-monitor/reference/tables/AppSystemEvents)<p>Application Insights system events. | applications | LogManagement | No| -|
| [AppTraces](/azure/azure-monitor/reference/tables/AppTraces)<p>Application Insights traces. | applications | LogManagement | No| -|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|

  
