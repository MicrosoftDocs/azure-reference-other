---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.datafactory/factories
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ADFActivityRun](/azure/azure-monitor/reference/tables/ADFActivityRun)<p> | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/adfactivityrun)|
| [ADFPipelineRun](/azure/azure-monitor/reference/tables/ADFPipelineRun)<p> | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/adfpipelinerun)|
| [ADFSSISIntegrationRuntimeLogs](/azure/azure-monitor/reference/tables/ADFSSISIntegrationRuntimeLogs)<p>ADF SSIS integration runtime logs | undefined | LogManagement | No| -|
| [ADFSSISPackageEventMessageContext](/azure/azure-monitor/reference/tables/ADFSSISPackageEventMessageContext)<p>ADF SSIS package execution event message context | undefined | LogManagement | No| -|
| [ADFSSISPackageEventMessages](/azure/azure-monitor/reference/tables/ADFSSISPackageEventMessages)<p>ADF SSIS package execution event messages | undefined | LogManagement | No| -|
| [ADFSSISPackageExecutableStatistics](/azure/azure-monitor/reference/tables/ADFSSISPackageExecutableStatistics)<p>ADF SSIS package execution executable statistics | undefined | LogManagement | No| -|
| [ADFSSISPackageExecutionComponentPhases](/azure/azure-monitor/reference/tables/ADFSSISPackageExecutionComponentPhases)<p>ADF SSIS package execution component phases | undefined | LogManagement | No| -|
| [ADFSSISPackageExecutionDataStatistics](/azure/azure-monitor/reference/tables/ADFSSISPackageExecutionDataStatistics)<p>ADF SSIS package execution data statistics | undefined | LogManagement | No| -|
| [ADFSandboxActivityRun](/azure/azure-monitor/reference/tables/ADFSandboxActivityRun)<p> | resources | LogManagement | No| -|
| [ADFSandboxPipelineRun](/azure/azure-monitor/reference/tables/ADFSandboxPipelineRun)<p> | resources | LogManagement | No| -|
| [ADFTriggerRun](/azure/azure-monitor/reference/tables/ADFTriggerRun)<p> | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/adftriggerrun)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

  
