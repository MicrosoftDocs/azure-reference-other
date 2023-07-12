---
title: Supported metrics - Microsoft.MachineLearningServices/workspaces
description: Reference for Microsoft.MachineLearningServices/workspaces metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.MachineLearningServices/workspaces  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.MachineLearningServices/workspaces resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Active Cores<p><p>Number of active cores |`Active Cores` |Count |Average |Scenario, ClusterName |Yes|
|Active Nodes<p><p>Number of Acitve nodes. These are the nodes which are actively running a job. |`Active Nodes` |Count |Average |Scenario, ClusterName |Yes|
|Cancel Requested Runs<p><p>Number of runs where cancel was requested for this workspace. Count is updated when cancellation request has been received for a run. |`Cancel Requested Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|Cancelled Runs<p><p>Number of runs cancelled for this workspace. Count is updated when a run is successfully cancelled. |`Cancelled Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|Completed Runs<p><p>Number of runs completed successfully for this workspace. Count is updated when a run has completed and output has been collected. |`Completed Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|CpuCapacityMillicores<p><p>Maximum capacity of a CPU node in millicores. Capacity is aggregated in one minute intervals. |`CpuCapacityMillicores` |Count |Average |RunId, InstanceId, ComputeName |Yes|
|CpuMemoryCapacityMegabytes<p><p>Maximum memory utilization of a CPU node in megabytes. Utilization is aggregated in one minute intervals. |`CpuMemoryCapacityMegabytes` |Count |Average |RunId, InstanceId, ComputeName |Yes|
|CpuMemoryUtilizationMegabytes<p><p>Memory utilization of a CPU node in megabytes. Utilization is aggregated in one minute intervals. |`CpuMemoryUtilizationMegabytes` |Count |Average |RunId, InstanceId, ComputeName |Yes|
|CpuMemoryUtilizationPercentage<p><p>Memory utilization percentage of a CPU node. Utilization is aggregated in one minute intervals. |`CpuMemoryUtilizationPercentage` |Count |Average |RunId, InstanceId, ComputeName |Yes|
|CpuUtilization<p><p>Percentage of utilization on a CPU node. Utilization is reported at one minute intervals. |`CpuUtilization` |Count |Average |Scenario, runId, NodeId, ClusterName |Yes|
|CpuUtilizationMillicores<p><p>Utilization of a CPU node in millicores. Utilization is aggregated in one minute intervals. |`CpuUtilizationMillicores` |Count |Average |RunId, InstanceId, ComputeName |Yes|
|CpuUtilizationPercentage<p><p>Utilization percentage of a CPU node. Utilization is aggregated in one minute intervals. |`CpuUtilizationPercentage` |Count |Average |RunId, InstanceId, ComputeName |Yes|
|DiskAvailMegabytes<p><p>Available disk space in megabytes. Metrics are aggregated in one minute intervals. |`DiskAvailMegabytes` |Count |Average |RunId, InstanceId, ComputeName |Yes|
|DiskReadMegabytes<p><p>Data read from disk in megabytes. Metrics are aggregated in one minute intervals. |`DiskReadMegabytes` |Count |Average |RunId, InstanceId, ComputeName |Yes|
|DiskUsedMegabytes<p><p>Used disk space in megabytes. Metrics are aggregated in one minute intervals. |`DiskUsedMegabytes` |Count |Average |RunId, InstanceId, ComputeName |Yes|
|DiskWriteMegabytes<p><p>Data written into disk in megabytes. Metrics are aggregated in one minute intervals. |`DiskWriteMegabytes` |Count |Average |RunId, InstanceId, ComputeName |Yes|
|Errors<p><p>Number of run errors in this workspace. Count is updated whenever run encounters an error. |`Errors` |Count |Total |Scenario |Yes|
|Failed Runs<p><p>Number of runs failed for this workspace. Count is updated when a run fails. |`Failed Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|Finalizing Runs<p><p>Number of runs entered finalizing state for this workspace. Count is updated when a run has completed but output collection still in progress. |`Finalizing Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|GpuCapacityMilliGPUs<p><p>Maximum capacity of a GPU device in milli-GPUs. Capacity is aggregated in one minute intervals. |`GpuCapacityMilliGPUs` |Count |Average |RunId, InstanceId, DeviceId, ComputeName |Yes|
|GpuEnergyJoules<p><p>Interval energy in Joules on a GPU node. Energy is reported at one minute intervals. |`GpuEnergyJoules` |Count |Total |Scenario, runId, rootRunId, InstanceId, DeviceId, ComputeName |Yes|
|GpuMemoryCapacityMegabytes<p><p>Maximum memory capacity of a GPU device in megabytes. Capacity aggregated in at one minute intervals. |`GpuMemoryCapacityMegabytes` |Count |Average |RunId, InstanceId, DeviceId, ComputeName |Yes|
|GpuMemoryUtilization<p><p>Percentage of memory utilization on a GPU node. Utilization is reported at one minute intervals. |`GpuMemoryUtilization` |Count |Average |Scenario, runId, NodeId, DeviceId, ClusterName |Yes|
|GpuMemoryUtilizationMegabytes<p><p>Memory utilization of a GPU device in megabytes. Utilization aggregated in at one minute intervals. |`GpuMemoryUtilizationMegabytes` |Count |Average |RunId, InstanceId, DeviceId, ComputeName |Yes|
|GpuMemoryUtilizationPercentage<p><p>Memory utilization percentage of a GPU device. Utilization aggregated in at one minute intervals. |`GpuMemoryUtilizationPercentage` |Count |Average |RunId, InstanceId, DeviceId, ComputeName |Yes|
|GpuUtilization<p><p>Percentage of utilization on a GPU node. Utilization is reported at one minute intervals. |`GpuUtilization` |Count |Average |Scenario, runId, NodeId, DeviceId, ClusterName |Yes|
|GpuUtilizationMilliGPUs<p><p>Utilization of a GPU device in milli-GPUs. Utilization is aggregated in one minute intervals. |`GpuUtilizationMilliGPUs` |Count |Average |RunId, InstanceId, DeviceId, ComputeName |Yes|
|GpuUtilizationPercentage<p><p>Utilization percentage of a GPU device. Utilization is aggregated in one minute intervals. |`GpuUtilizationPercentage` |Count |Average |RunId, InstanceId, DeviceId, ComputeName |Yes|
|IBReceiveMegabytes<p><p>Network data received over InfiniBand in megabytes. Metrics are aggregated in one minute intervals. |`IBReceiveMegabytes` |Count |Average |RunId, InstanceId, ComputeName, DeviceId |Yes|
|IBTransmitMegabytes<p><p>Network data sent over InfiniBand in megabytes. Metrics are aggregated in one minute intervals. |`IBTransmitMegabytes` |Count |Average |RunId, InstanceId, ComputeName, DeviceId |Yes|
|Idle Cores<p><p>Number of idle cores |`Idle Cores` |Count |Average |Scenario, ClusterName |Yes|
|Idle Nodes<p><p>Number of idle nodes. Idle nodes are the nodes which are not running any jobs but can accept new job if available. |`Idle Nodes` |Count |Average |Scenario, ClusterName |Yes|
|Leaving Cores<p><p>Number of leaving cores |`Leaving Cores` |Count |Average |Scenario, ClusterName |Yes|
|Leaving Nodes<p><p>Number of leaving nodes. Leaving nodes are the nodes which just finished processing a job and will go to Idle state. |`Leaving Nodes` |Count |Average |Scenario, ClusterName |Yes|
|Model Deploy Failed<p><p>Number of model deployments that failed in this workspace |`Model Deploy Failed` |Count |Total |Scenario, StatusCode |Yes|
|Model Deploy Started<p><p>Number of model deployments started in this workspace |`Model Deploy Started` |Count |Total |Scenario |Yes|
|Model Deploy Succeeded<p><p>Number of model deployments that succeeded in this workspace |`Model Deploy Succeeded` |Count |Total |Scenario |Yes|
|Model Register Failed<p><p>Number of model registrations that failed in this workspace |`Model Register Failed` |Count |Total |Scenario, StatusCode |Yes|
|Model Register Succeeded<p><p>Number of model registrations that succeeded in this workspace |`Model Register Succeeded` |Count |Total |Scenario |Yes|
|NetworkInputMegabytes<p><p>Network data received in megabytes. Metrics are aggregated in one minute intervals. |`NetworkInputMegabytes` |Count |Average |RunId, InstanceId, ComputeName, DeviceId |Yes|
|NetworkOutputMegabytes<p><p>Network data sent in megabytes. Metrics are aggregated in one minute intervals. |`NetworkOutputMegabytes` |Count |Average |RunId, InstanceId, ComputeName, DeviceId |Yes|
|Not Responding Runs<p><p>Number of runs not responding for this workspace. Count is updated when a run enters Not Responding state. |`Not Responding Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|Not Started Runs<p><p>Number of runs in Not Started state for this workspace. Count is updated when a request is received to create a run but run information has not yet been populated.  |`Not Started Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|Preempted Cores<p><p>Number of preempted cores |`Preempted Cores` |Count |Average |Scenario, ClusterName |Yes|
|Preempted Nodes<p><p>Number of preempted nodes. These nodes are the low priority nodes which are taken away from the available node pool. |`Preempted Nodes` |Count |Average |Scenario, ClusterName |Yes|
|Preparing Runs<p><p>Number of runs that are preparing for this workspace. Count is updated when a run enters Preparing state while the run environment is being prepared. |`Preparing Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|Provisioning Runs<p><p>Number of runs that are provisioning for this workspace. Count is updated when a run is waiting on compute target creation or provisioning. |`Provisioning Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|Queued Runs<p><p>Number of runs that are queued for this workspace. Count is updated when a run is queued in compute target. Can occure when waiting for required compute nodes to be ready. |`Queued Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|Quota Utilization Percentage<p><p>Percent of quota utilized |`Quota Utilization Percentage` |Count |Average |Scenario, ClusterName, VmFamilyName, VmPriority |Yes|
|Started Runs<p><p>Number of runs running for this workspace. Count is updated when run starts running on required resources. |`Started Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|Starting Runs<p><p>Number of runs started for this workspace. Count is updated after request to create run and run info, such as the Run Id, has been populated |`Starting Runs` |Count |Total |Scenario, RunType, PublishedPipelineId, ComputeType, PipelineStepType, ExperimentName |Yes|
|StorageAPIFailureCount<p><p>Azure Blob Storage API calls failure count. |`StorageAPIFailureCount` |Count |Total |RunId, InstanceId, ComputeName |Yes|
|StorageAPISuccessCount<p><p>Azure Blob Storage API calls success count. |`StorageAPISuccessCount` |Count |Total |RunId, InstanceId, ComputeName |Yes|
|Total Cores<p><p>Number of total cores |`Total Cores` |Count |Average |Scenario, ClusterName |Yes|
|Total Nodes<p><p>Number of total nodes. This total includes some of Active Nodes, Idle Nodes, Unusable Nodes, Premepted Nodes, Leaving Nodes |`Total Nodes` |Count |Average |Scenario, ClusterName |Yes|
|Unusable Cores<p><p>Number of unusable cores |`Unusable Cores` |Count |Average |Scenario, ClusterName |Yes|
|Unusable Nodes<p><p>Number of unusable nodes. Unusable nodes are not functional due to some unresolvable issue. Azure will recycle these nodes. |`Unusable Nodes` |Count |Average |Scenario, ClusterName |Yes|
|Warnings<p><p>Number of run warnings in this workspace. Count is updated whenever a run encounters a warning. |`Warnings` |Count |Total |Scenario |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->