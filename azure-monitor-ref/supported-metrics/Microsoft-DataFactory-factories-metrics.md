---
title: Supported metrics - Microsoft.DataFactory/factories
description: Reference for Microsoft.DataFactory/factories metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DataFactory/factories  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.DataFactory/factories resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Cancelled activity runs metrics<p><p>Cancelled activity runs metrics |`ActivityCancelledRuns` |Count |Total |ActivityType, PipelineName, FailureType, Name |Yes|
|Failed activity runs metrics<p><p>Failed activity runs metrics |`ActivityFailedRuns` |Count |Total |ActivityType, PipelineName, FailureType, Name |Yes|
|Succeeded activity runs metrics<p><p>Succeeded activity runs metrics |`ActivitySucceededRuns` |Count |Total |ActivityType, PipelineName, FailureType, Name |Yes|
|Airflow Integration Runtime Celery Task Timeout Error<p><p>Airflow Integration Runtime Celery Task Timeout Error |`AirflowIntegrationRuntimeCeleryTaskTimeoutError` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Collect DB Dags<p><p>Airflow Integration Runtime Collect DB Dags |`AirflowIntegrationRuntimeCollectDBDags` |Milliseconds |Average |IntegrationRuntimeName |No|
|Airflow Integration Runtime Cpu Percentage<p><p>Airflow Integration Runtime Cpu Percentage |`AirflowIntegrationRuntimeCpuPercentage` |Percent |Average |IntegrationRuntimeName, ContainerName |No|
|Airflow Integration Runtime Memory Usage<p><p>Airflow Integration Runtime Memory Usage |`AirflowIntegrationRuntimeCpuUsage` |Millicores |Average |IntegrationRuntimeName, ContainerName |Yes|
|Airflow Integration Runtime Dag Bag Size<p><p>Airflow Integration Runtime Dag Bag Size |`AirflowIntegrationRuntimeDagBagSize` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Dag Callback Exceptions<p><p>Airflow Integration Runtime Dag Callback Exceptions |`AirflowIntegrationRuntimeDagCallbackExceptions` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime DAG File Refresh Error<p><p>Airflow Integration Runtime DAG File Refresh Error |`AirflowIntegrationRuntimeDAGFileRefreshError` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime DAG Processing Import Errors<p><p>Airflow Integration Runtime DAG Processing Import Errors |`AirflowIntegrationRuntimeDAGProcessingImportErrors` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime DAG Processing Last Duration<p><p>Airflow Integration Runtime DAG Processing Last Duration |`AirflowIntegrationRuntimeDAGProcessingLastDuration` |Milliseconds |Average |IntegrationRuntimeName, DagFile |No|
|Airflow Integration Runtime DAG Processing Last Run Seconds Ago<p><p>Airflow Integration Runtime DAG Processing Last Run Seconds Ago |`AirflowIntegrationRuntimeDAGProcessingLastRunSecondsAgo` |Seconds |Average |IntegrationRuntimeName, DagFile |No|
|Airflow Integration Runtime DAG ProcessingManager Stalls<p><p>Airflow Integration Runtime DAG ProcessingManager Stalls |`AirflowIntegrationRuntimeDAGProcessingManagerStalls` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime DAG Processing Processes<p><p>Airflow Integration Runtime DAG Processing Processes |`AirflowIntegrationRuntimeDAGProcessingProcesses` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime DAG Processing Processor Timeouts<p><p>Airflow Integration Runtime DAG Processing Processor Timeouts |`AirflowIntegrationRuntimeDAGProcessingProcessorTimeouts` |Seconds |Average |IntegrationRuntimeName |No|
|Airflow Integration Runtime DAG Processing Total Parse Time<p><p>Airflow Integration Runtime DAG Processing Total Parse Time |`AirflowIntegrationRuntimeDAGProcessingTotalParseTime` |Seconds |Average |IntegrationRuntimeName |No|
|Airflow Integration Runtime DAG Run Dependency Check<p><p>Airflow Integration Runtime DAG Run Dependency Check |`AirflowIntegrationRuntimeDAGRunDependencyCheck` |Milliseconds |Average |IntegrationRuntimeName, DagId |No|
|Airflow Integration Runtime DAG Run Duration Failed<p><p>Airflow Integration Runtime DAG Run Duration Failed |`AirflowIntegrationRuntimeDAGRunDurationFailed` |Milliseconds |Average |IntegrationRuntimeName, DagId |No|
|Airflow Integration Runtime DAG Run Duration Success<p><p>Airflow Integration Runtime DAG Run Duration Success |`AirflowIntegrationRuntimeDAGRunDurationSuccess` |Milliseconds |Average |IntegrationRuntimeName, DagId |No|
|Airflow Integration Runtime DAG Run First Task Scheduling Delay<p><p>Airflow Integration Runtime DAG Run First Task Scheduling Delay |`AirflowIntegrationRuntimeDAGRunFirstTaskSchedulingDelay` |Milliseconds |Average |IntegrationRuntimeName, DagId |No|
|Airflow Integration Runtime DAG Run Schedule Delay<p><p>Airflow Integration Runtime DAG Run Schedule Delay |`AirflowIntegrationRuntimeDAGRunScheduleDelay` |Milliseconds |Average |IntegrationRuntimeName, DagId |No|
|Airflow Integration Runtime Executor Open Slots<p><p>Airflow Integration Runtime Executor Open Slots |`AirflowIntegrationRuntimeExecutorOpenSlots` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Executor Queued Tasks<p><p>Airflow Integration Runtime Executor Queued Tasks |`AirflowIntegrationRuntimeExecutorQueuedTasks` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Executor Running Tasks<p><p>Airflow Integration Runtime Executor Running Tasks |`AirflowIntegrationRuntimeExecutorRunningTasks` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Job End<p><p>Airflow Integration Runtime Job End |`AirflowIntegrationRuntimeJobEnd` |Count |Total |IntegrationRuntimeName, Job |No|
|Airflow Integration Runtime Heartbeat Failure<p><p>Airflow Integration Runtime Heartbeat Failure |`AirflowIntegrationRuntimeJobHeartbeatFailure` |Count |Total |IntegrationRuntimeName, Job |No|
|Airflow Integration Runtime Job Start<p><p>Airflow Integration Runtime Job Start |`AirflowIntegrationRuntimeJobStart` |Count |Total |IntegrationRuntimeName, Job |No|
|Airflow Integration Runtime Memory Percentage<p><p>Airflow Integration Runtime Memory Percentage |`AirflowIntegrationRuntimeMemoryPercentage` |Percent |Average |IntegrationRuntimeName, ContainerName |Yes|
|Airflow Integration Runtime Operator Failures<p><p>Airflow Integration Runtime Operator Failures |`AirflowIntegrationRuntimeOperatorFailures` |Count |Total |IntegrationRuntimeName, Operator |No|
|Airflow Integration Runtime Operator Successes<p><p>Airflow Integration Runtime Operator Successes |`AirflowIntegrationRuntimeOperatorSuccesses` |Count |Total |IntegrationRuntimeName, Operator |No|
|Airflow Integration Runtime Pool Open Slots<p><p>Airflow Integration Runtime Pool Open Slots |`AirflowIntegrationRuntimePoolOpenSlots` |Count |Total |IntegrationRuntimeName, Pool |No|
|Airflow Integration Runtime Pool Queued Slots<p><p>Airflow Integration Runtime Pool Queued Slots |`AirflowIntegrationRuntimePoolQueuedSlots` |Count |Total |IntegrationRuntimeName, Pool |No|
|Airflow Integration Runtime Pool Running Slots<p><p>Airflow Integration Runtime Pool Running Slots |`AirflowIntegrationRuntimePoolRunningSlots` |Count |Total |IntegrationRuntimeName, Pool |No|
|Airflow Integration Runtime Pool Starving Tasks<p><p>Airflow Integration Runtime Pool Starving Tasks |`AirflowIntegrationRuntimePoolStarvingTasks` |Count |Total |IntegrationRuntimeName, Pool |No|
|Airflow Integration Runtime Scheduler Critical Section Busy<p><p>Airflow Integration Runtime Scheduler Critical Section Busy |`AirflowIntegrationRuntimeSchedulerCriticalSectionBusy` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Scheduler Critical Section Duration<p><p>Airflow Integration Runtime Scheduler Critical Section Duration |`AirflowIntegrationRuntimeSchedulerCriticalSectionDuration` |Milliseconds |Average |IntegrationRuntimeName |No|
|Airflow Integration Runtime Scheduler Failed SLA Email Attempts<p><p>Airflow Integration Runtime Scheduler Failed SLA Email Attempts |`AirflowIntegrationRuntimeSchedulerFailedSLAEmailAttempts` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Scheduler Heartbeats<p><p>Airflow Integration Runtime Scheduler Heartbeats |`AirflowIntegrationRuntimeSchedulerHeartbeat` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Scheduler Orphaned Tasks Adopted<p><p>Airflow Integration Runtime Scheduler Orphaned Tasks Adopted |`AirflowIntegrationRuntimeSchedulerOrphanedTasksAdopted` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Scheduler Orphaned Tasks Cleared<p><p>Airflow Integration Runtime Scheduler Orphaned Tasks Cleared |`AirflowIntegrationRuntimeSchedulerOrphanedTasksCleared` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Scheduler Tasks Executable<p><p>Airflow Integration Runtime Scheduler Tasks Executable |`AirflowIntegrationRuntimeSchedulerTasksExecutable` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Scheduler Tasks Killed Externally<p><p>Airflow Integration Runtime Scheduler Tasks Killed Externally |`AirflowIntegrationRuntimeSchedulerTasksKilledExternally` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Scheduler Tasks Running<p><p>Airflow Integration Runtime Scheduler Tasks Running |`AirflowIntegrationRuntimeSchedulerTasksRunning` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Scheduler Tasks Starving<p><p>Airflow Integration Runtime Scheduler Tasks Starving |`AirflowIntegrationRuntimeSchedulerTasksStarving` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Started Task Instances<p><p>Airflow Integration Runtime Started Task Instances |`AirflowIntegrationRuntimeStartedTaskInstances` |Count |Total |IntegrationRuntimeName, DagId, TaskId |No|
|Airflow Integration Runtime Task Instance Created Using Operator<p><p>Airflow Integration Runtime Task Instance Created Using Operator |`AirflowIntegrationRuntimeTaskInstanceCreatedUsingOperator` |Count |Total |IntegrationRuntimeName, Operator |No|
|Airflow Integration Runtime Task Instance Duration<p><p>Airflow Integration Runtime Task Instance Duration |`AirflowIntegrationRuntimeTaskInstanceDuration` |Milliseconds |Average |IntegrationRuntimeName, DagId, TaskID |No|
|Airflow Integration Runtime Task Instance Failures<p><p>Airflow Integration Runtime Task Instance Failures |`AirflowIntegrationRuntimeTaskInstanceFailures` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Task Instance Finished<p><p>Airflow Integration Runtime Task Instance Finished |`AirflowIntegrationRuntimeTaskInstanceFinished` |Count |Total |IntegrationRuntimeName, DagId, TaskId, State |No|
|Airflow Integration Runtime Task Instance Previously Succeeded<p><p>Airflow Integration Runtime Task Instance Previously Succeeded |`AirflowIntegrationRuntimeTaskInstancePreviouslySucceeded` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Task Instance Successes<p><p>Airflow Integration Runtime Task Instance Successes |`AirflowIntegrationRuntimeTaskInstanceSuccesses` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Task Removed From DAG<p><p>Airflow Integration Runtime Task Removed From DAG |`AirflowIntegrationRuntimeTaskRemovedFromDAG` |Count |Total |IntegrationRuntimeName, DagId |No|
|Airflow Integration Runtime Task Restored To DAG<p><p>Airflow Integration Runtime Task Restored To DAG |`AirflowIntegrationRuntimeTaskRestoredToDAG` |Count |Total |IntegrationRuntimeName, DagId |No|
|Airflow Integration Runtime Triggers Blocked Main Thread<p><p>Airflow Integration Runtime Triggers Blocked Main Thread |`AirflowIntegrationRuntimeTriggersBlockedMainThread` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Triggers Failed<p><p>Airflow Integration Runtime Triggers Failed |`AirflowIntegrationRuntimeTriggersFailed` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Triggers Running<p><p>Airflow Integration Runtime Triggers Running |`AirflowIntegrationRuntimeTriggersRunning` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Triggers Succeeded<p><p>Airflow Integration Runtime Triggers Succeeded |`AirflowIntegrationRuntimeTriggersSucceeded` |Count |Total |IntegrationRuntimeName |No|
|Airflow Integration Runtime Zombie Tasks Killed<p><p>Airflow Integration Runtime Zombie Tasks Killed |`AirflowIntegrationRuntimeZombiesKilled` |Count |Total |IntegrationRuntimeName |No|
|Total factory size (GB unit)<p><p>Total factory size (GB unit) |`FactorySizeInGbUnits` |Count |Maximum |No Dimensions |Yes|
|Integration runtime available memory<p><p>Integration runtime available memory |`IntegrationRuntimeAvailableMemory` |Bytes |Average |IntegrationRuntimeName, NodeName |Yes|
|Integration runtime available node count<p><p>Integration runtime available node count |`IntegrationRuntimeAvailableNodeNumber` |Count |Average |IntegrationRuntimeName |Yes|
|Integration runtime queue duration<p><p>Integration runtime queue duration |`IntegrationRuntimeAverageTaskPickupDelay` |Seconds |Average |IntegrationRuntimeName |Yes|
|Integration runtime CPU utilization<p><p>Integration runtime CPU utilization |`IntegrationRuntimeCpuPercentage` |Percent |Average |IntegrationRuntimeName, NodeName |Yes|
|Integration runtime queue length<p><p>Integration runtime queue length |`IntegrationRuntimeQueueLength` |Count |Average |IntegrationRuntimeName |Yes|
|Maximum allowed factory size (GB unit)<p><p>Maximum allowed factory size (GB unit) |`MaxAllowedFactorySizeInGbUnits` |Count |Maximum |No Dimensions |Yes|
|Maximum allowed entities count<p><p>Maximum allowed entities count |`MaxAllowedResourceCount` |Count |Maximum |No Dimensions |Yes|
|Cancelled pipeline runs metrics<p><p>Cancelled pipeline runs metrics |`PipelineCancelledRuns` |Count |Total |FailureType, CancelledBy, Name |Yes|
|Elapsed Time Pipeline Runs Metrics<p><p>Elapsed Time Pipeline Runs Metrics |`PipelineElapsedTimeRuns` |Count |Total |RunId, Name |Yes|
|Failed pipeline runs metrics<p><p>Failed pipeline runs metrics |`PipelineFailedRuns` |Count |Total |FailureType, Name |Yes|
|Succeeded pipeline runs metrics<p><p>Succeeded pipeline runs metrics |`PipelineSucceededRuns` |Count |Total |FailureType, Name |Yes|
|Total entities count<p><p>Total entities count |`ResourceCount` |Count |Maximum |No Dimensions |Yes|
|Cancelled SSIS integration runtime start metrics<p><p>Cancelled SSIS integration runtime start metrics |`SSISIntegrationRuntimeStartCancel` |Count |Total |IntegrationRuntimeName |Yes|
|Failed SSIS integration runtime start metrics<p><p>Failed SSIS integration runtime start metrics |`SSISIntegrationRuntimeStartFailed` |Count |Total |IntegrationRuntimeName |Yes|
|Succeeded SSIS integration runtime start metrics<p><p>Succeeded SSIS integration runtime start metrics |`SSISIntegrationRuntimeStartSucceeded` |Count |Total |IntegrationRuntimeName |Yes|
|Stuck SSIS integration runtime stop metrics<p><p>Stuck SSIS integration runtime stop metrics |`SSISIntegrationRuntimeStopStuck` |Count |Total |IntegrationRuntimeName |Yes|
|Succeeded SSIS integration runtime stop metrics<p><p>Succeeded SSIS integration runtime stop metrics |`SSISIntegrationRuntimeStopSucceeded` |Count |Total |IntegrationRuntimeName |Yes|
|Cancelled SSIS package execution metrics<p><p>Cancelled SSIS package execution metrics |`SSISPackageExecutionCancel` |Count |Total |IntegrationRuntimeName |Yes|
|Failed SSIS package execution metrics<p><p>Failed SSIS package execution metrics |`SSISPackageExecutionFailed` |Count |Total |IntegrationRuntimeName |Yes|
|Succeeded SSIS package execution metrics<p><p>Succeeded SSIS package execution metrics |`SSISPackageExecutionSucceeded` |Count |Total |IntegrationRuntimeName |Yes|
|Cancelled trigger runs metrics<p><p>Cancelled trigger runs metrics |`TriggerCancelledRuns` |Count |Total |Name, FailureType |Yes|
|Failed trigger runs metrics<p><p>Failed trigger runs metrics |`TriggerFailedRuns` |Count |Total |Name, FailureType |Yes|
|Succeeded trigger runs metrics<p><p>Succeeded trigger runs metrics |`TriggerSucceededRuns` |Count |Total |Name, FailureType |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->