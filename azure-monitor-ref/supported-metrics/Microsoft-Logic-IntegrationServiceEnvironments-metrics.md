---
title: Supported metrics - Microsoft.Logic/IntegrationServiceEnvironments
description: Reference for Microsoft.Logic/IntegrationServiceEnvironments metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Logic/IntegrationServiceEnvironments  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Logic/IntegrationServiceEnvironments resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Action Latency <p><p>Latency of completed workflow actions. |`ActionLatency` |Seconds |Average |No Dimensions |Yes|
|Actions Completed <p><p>Number of workflow actions completed. |`ActionsCompleted` |Count |Total |No Dimensions |Yes|
|Actions Failed <p><p>Number of workflow actions failed. |`ActionsFailed` |Count |Total |No Dimensions |Yes|
|Actions Skipped <p><p>Number of workflow actions skipped. |`ActionsSkipped` |Count |Total |No Dimensions |Yes|
|Actions Started <p><p>Number of workflow actions started. |`ActionsStarted` |Count |Total |No Dimensions |Yes|
|Actions Succeeded <p><p>Number of workflow actions succeeded. |`ActionsSucceeded` |Count |Total |No Dimensions |Yes|
|Action Success Latency <p><p>Latency of succeeded workflow actions. |`ActionSuccessLatency` |Seconds |Average |No Dimensions |Yes|
|Connector Memory Usage for Integration Service Environment<p><p>Connector memory usage for integration service environment. |`IntegrationServiceEnvironmentConnectorMemoryUsage` |Percent |Average |No Dimensions |Yes|
|Connector Processor Usage for Integration Service Environment<p><p>Connector processor usage for integration service environment. |`IntegrationServiceEnvironmentConnectorProcessorUsage` |Percent |Average |No Dimensions |Yes|
|Workflow Memory Usage for Integration Service Environment<p><p>Workflow memory usage for integration service environment. |`IntegrationServiceEnvironmentWorkflowMemoryUsage` |Percent |Average |No Dimensions |Yes|
|Workflow Processor Usage for Integration Service Environment<p><p>Workflow processor usage for integration service environment. |`IntegrationServiceEnvironmentWorkflowProcessorUsage` |Percent |Average |No Dimensions |Yes|
|Run Latency<p><p>Latency of completed workflow runs. |`RunLatency` |Seconds |Average |No Dimensions |Yes|
|Runs Cancelled<p><p>Number of workflow runs cancelled. |`RunsCancelled` |Count |Total |No Dimensions |Yes|
|Runs Completed<p><p>Number of workflow runs completed. |`RunsCompleted` |Count |Total |No Dimensions |Yes|
|Runs Failed<p><p>Number of workflow runs failed. |`RunsFailed` |Count |Total |No Dimensions |Yes|
|Runs Started<p><p>Number of workflow runs started. |`RunsStarted` |Count |Total |No Dimensions |Yes|
|Runs Succeeded<p><p>Number of workflow runs succeeded. |`RunsSucceeded` |Count |Total |No Dimensions |Yes|
|Run Success Latency<p><p>Latency of succeeded workflow runs. |`RunSuccessLatency` |Seconds |Average |No Dimensions |Yes|
|Trigger Fire Latency <p><p>Latency of fired workflow triggers. |`TriggerFireLatency` |Seconds |Average |No Dimensions |Yes|
|Trigger Latency <p><p>Latency of completed workflow triggers. |`TriggerLatency` |Seconds |Average |No Dimensions |Yes|
|Triggers Completed <p><p>Number of workflow triggers completed. |`TriggersCompleted` |Count |Total |No Dimensions |Yes|
|Triggers Failed <p><p>Number of workflow triggers failed. |`TriggersFailed` |Count |Total |No Dimensions |Yes|
|Triggers Fired <p><p>Number of workflow triggers fired. |`TriggersFired` |Count |Total |No Dimensions |Yes|
|Triggers Skipped<p><p>Number of workflow triggers skipped. |`TriggersSkipped` |Count |Total |No Dimensions |Yes|
|Triggers Started <p><p>Number of workflow triggers started. |`TriggersStarted` |Count |Total |No Dimensions |Yes|
|Triggers Succeeded <p><p>Number of workflow triggers succeeded. |`TriggersSucceeded` |Count |Total |No Dimensions |Yes|
|Trigger Success Latency <p><p>Latency of succeeded workflow triggers. |`TriggerSuccessLatency` |Seconds |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->