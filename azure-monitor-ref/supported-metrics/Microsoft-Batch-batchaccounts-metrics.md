---
title: Supported metrics - Microsoft.Batch/batchaccounts
description: Reference for Microsoft.Batch/batchaccounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Batch/batchaccounts  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Batch/batchaccounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Dedicated Core Count<p><p>Total number of dedicated cores in the batch account |`CoreCount` |Count |Total |No Dimensions |No|
|Creating Node Count<p><p>Number of nodes being created |`CreatingNodeCount` |Count |Total |No Dimensions |No|
|Idle Node Count<p><p>Number of idle nodes |`IdleNodeCount` |Count |Total |No Dimensions |No|
|Job Delete Complete Events<p><p>Total number of jobs that have been successfully deleted. |`JobDeleteCompleteEvent` |Count |Total |jobId |Yes|
|Job Delete Start Events<p><p>Total number of jobs that have been requested to be deleted. |`JobDeleteStartEvent` |Count |Total |jobId |Yes|
|Job Disable Complete Events<p><p>Total number of jobs that have been successfully disabled. |`JobDisableCompleteEvent` |Count |Total |jobId |Yes|
|Job Disable Start Events<p><p>Total number of jobs that have been requested to be disabled. |`JobDisableStartEvent` |Count |Total |jobId |Yes|
|Job Start Events<p><p>Total number of jobs that have been successfully started. |`JobStartEvent` |Count |Total |jobId |Yes|
|Job Terminate Complete Events<p><p>Total number of jobs that have been successfully terminated. |`JobTerminateCompleteEvent` |Count |Total |jobId |Yes|
|Job Terminate Start Events<p><p>Total number of jobs that have been requested to be terminated. |`JobTerminateStartEvent` |Count |Total |jobId |Yes|
|Leaving Pool Node Count<p><p>Number of nodes leaving the Pool |`LeavingPoolNodeCount` |Count |Total |No Dimensions |No|
|LowPriority Core Count<p><p>Total number of low-priority cores in the batch account |`LowPriorityCoreCount` |Count |Total |No Dimensions |No|
|Offline Node Count<p><p>Number of offline nodes |`OfflineNodeCount` |Count |Total |No Dimensions |No|
|Pool Create Events<p><p>Total number of pools that have been created |`PoolCreateEvent` |Count |Total |poolId |Yes|
|Pool Delete Complete Events<p><p>Total number of pool deletes that have completed |`PoolDeleteCompleteEvent` |Count |Total |poolId |Yes|
|Pool Delete Start Events<p><p>Total number of pool deletes that have started |`PoolDeleteStartEvent` |Count |Total |poolId |Yes|
|Pool Resize Complete Events<p><p>Total number of pool resizes that have completed |`PoolResizeCompleteEvent` |Count |Total |poolId |Yes|
|Pool Resize Start Events<p><p>Total number of pool resizes that have started |`PoolResizeStartEvent` |Count |Total |poolId |Yes|
|Preempted Node Count<p><p>Number of preempted nodes |`PreemptedNodeCount` |Count |Total |No Dimensions |No|
|Rebooting Node Count<p><p>Number of rebooting nodes |`RebootingNodeCount` |Count |Total |No Dimensions |No|
|Reimaging Node Count<p><p>Number of reimaging nodes |`ReimagingNodeCount` |Count |Total |No Dimensions |No|
|Running Node Count<p><p>Number of running nodes |`RunningNodeCount` |Count |Total |No Dimensions |No|
|Starting Node Count<p><p>Number of nodes starting |`StartingNodeCount` |Count |Total |No Dimensions |No|
|Start Task Failed Node Count<p><p>Number of nodes where the Start Task has failed |`StartTaskFailedNodeCount` |Count |Total |No Dimensions |No|
|Task Complete Events<p><p>Total number of tasks that have completed |`TaskCompleteEvent` |Count |Total |poolId, jobId |Yes|
|Task Fail Events<p><p>Total number of tasks that have completed in a failed state |`TaskFailEvent` |Count |Total |poolId, jobId |Yes|
|Task Start Events<p><p>Total number of tasks that have started |`TaskStartEvent` |Count |Total |poolId, jobId |Yes|
|Low-Priority Node Count<p><p>Total number of low-priority nodes in the batch account |`TotalLowPriorityNodeCount` |Count |Total |No Dimensions |No|
|Dedicated Node Count<p><p>Total number of dedicated nodes in the batch account |`TotalNodeCount` |Count |Total |No Dimensions |No|
|Unusable Node Count<p><p>Number of unusable nodes |`UnusableNodeCount` |Count |Total |No Dimensions |No|
|Waiting For Start Task Node Count<p><p>Number of nodes waiting for the Start Task to complete |`WaitingForStartTaskNodeCount` |Count |Total |No Dimensions |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->