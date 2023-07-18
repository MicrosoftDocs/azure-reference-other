---
title: Supported metrics - Microsoft.Logic/Workflows
description: Reference for Microsoft.Logic/Workflows metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Logic/Workflows  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Logic/Workflows resource type.

  

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
|Action Throttled Events<p><p>Number of workflow action throttled events.. |`ActionThrottledEvents` |Count |Total |No Dimensions |Yes|
|Billable Action Executions<p><p>Number of workflow action executions getting billed. |`BillableActionExecutions` |Count |Total |No Dimensions |Yes|
|Billable Trigger Executions<p><p>Number of workflow trigger executions getting billed. |`BillableTriggerExecutions` |Count |Total |No Dimensions |Yes|
|Billing Usage for Native Operation Executions<p><p>Number of native operation executions getting billed. |`BillingUsageNativeOperation` |Count |Total |No Dimensions |Yes|
|Billing Usage for Standard Connector Executions<p><p>Number of standard connector executions getting billed. |`BillingUsageStandardConnector` |Count |Total |No Dimensions |Yes|
|Billing Usage for Storage Consumption Executions<p><p>Number of storage consumption executions getting billed. |`BillingUsageStorageConsumption` |Count |Total |No Dimensions |Yes|
|Run Failure Percentage<p><p>Percentage of workflow runs failed. |`RunFailurePercentage` |Percent |Total |No Dimensions |Yes|
|Run Latency<p><p>Latency of completed workflow runs. |`RunLatency` |Seconds |Average |No Dimensions |Yes|
|Runs Cancelled<p><p>Number of workflow runs cancelled. |`RunsCancelled` |Count |Total |No Dimensions |Yes|
|Runs Completed<p><p>Number of workflow runs completed. |`RunsCompleted` |Count |Total |No Dimensions |Yes|
|Runs Failed<p><p>Number of workflow runs failed. |`RunsFailed` |Count |Total |No Dimensions |Yes|
|Runs Started<p><p>Number of workflow runs started. |`RunsStarted` |Count |Total |No Dimensions |Yes|
|Runs Succeeded<p><p>Number of workflow runs succeeded. |`RunsSucceeded` |Count |Total |No Dimensions |Yes|
|Run Start Throttled Events<p><p>Number of workflow run start throttled events. |`RunStartThrottledEvents` |Count |Total |No Dimensions |Yes|
|Run Success Latency<p><p>Latency of succeeded workflow runs. |`RunSuccessLatency` |Seconds |Average |No Dimensions |Yes|
|Run Throttled Events<p><p>Number of workflow action or trigger throttled events. |`RunThrottledEvents` |Count |Total |No Dimensions |Yes|
|Total Billable Executions<p><p>Number of workflow executions getting billed. |`TotalBillableExecutions` |Count |Total |No Dimensions |Yes|
|Trigger Fire Latency <p><p>Latency of fired workflow triggers. |`TriggerFireLatency` |Seconds |Average |No Dimensions |Yes|
|Trigger Latency <p><p>Latency of completed workflow triggers. |`TriggerLatency` |Seconds |Average |No Dimensions |Yes|
|Triggers Completed <p><p>Number of workflow triggers completed. |`TriggersCompleted` |Count |Total |No Dimensions |Yes|
|Triggers Failed <p><p>Number of workflow triggers failed. |`TriggersFailed` |Count |Total |No Dimensions |Yes|
|Triggers Fired <p><p>Number of workflow triggers fired. |`TriggersFired` |Count |Total |No Dimensions |Yes|
|Triggers Skipped<p><p>Number of workflow triggers skipped. |`TriggersSkipped` |Count |Total |No Dimensions |Yes|
|Triggers Started <p><p>Number of workflow triggers started. |`TriggersStarted` |Count |Total |No Dimensions |Yes|
|Triggers Succeeded <p><p>Number of workflow triggers succeeded. |`TriggersSucceeded` |Count |Total |No Dimensions |Yes|
|Trigger Success Latency <p><p>Latency of succeeded workflow triggers. |`TriggerSuccessLatency` |Seconds |Average |No Dimensions |Yes|
|Trigger Throttled Events<p><p>Number of workflow trigger throttled events. |`TriggerThrottledEvents` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->