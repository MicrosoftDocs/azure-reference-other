---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataFactory/factories, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Cancelled activity runs metrics**<p><p>Cancelled activity runs metrics |`ActivityCancelledRuns` |Count |Total |`ActivityType`, `PipelineName`, `FailureType`, `Name`|PT1M |Yes|
|**Failed activity runs metrics**<p><p>Failed activity runs metrics |`ActivityFailedRuns` |Count |Total |`ActivityType`, `PipelineName`, `FailureType`, `Name`|PT1M |Yes|
|**Succeeded activity runs metrics**<p><p>Succeeded activity runs metrics |`ActivitySucceededRuns` |Count |Total |`ActivityType`, `PipelineName`, `FailureType`, `Name`|PT1M |Yes|
|**Airflow Integration Runtime Celery Task Timeout Error**<p><p>Airflow Integration Runtime Celery Task Timeout Error |`AirflowIntegrationRuntimeCeleryTaskTimeoutError` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Collect DB Dags**<p><p>Airflow Integration Runtime Collect DB Dags |`AirflowIntegrationRuntimeCollectDBDags` |Milliseconds |Average |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Cpu Percentage**<p><p>Airflow Integration Runtime Cpu Percentage |`AirflowIntegrationRuntimeCpuPercentage` |Percent |Average |`IntegrationRuntimeName`, `ContainerName`|PT1M |No|
|**Airflow Integration Runtime Memory Usage**<p><p>Airflow Integration Runtime Memory Usage |`AirflowIntegrationRuntimeCpuUsage` |Millicores |Average |`IntegrationRuntimeName`, `ContainerName`|PT1M |Yes|
|**Airflow Integration Runtime Dag Bag Size**<p><p>Airflow Integration Runtime Dag Bag Size |`AirflowIntegrationRuntimeDagBagSize` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Dag Callback Exceptions**<p><p>Airflow Integration Runtime Dag Callback Exceptions |`AirflowIntegrationRuntimeDagCallbackExceptions` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime DAG File Refresh Error**<p><p>Airflow Integration Runtime DAG File Refresh Error |`AirflowIntegrationRuntimeDAGFileRefreshError` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime DAG Processing Import Errors**<p><p>Airflow Integration Runtime DAG Processing Import Errors |`AirflowIntegrationRuntimeDAGProcessingImportErrors` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime DAG Processing Last Duration**<p><p>Airflow Integration Runtime DAG Processing Last Duration |`AirflowIntegrationRuntimeDAGProcessingLastDuration` |Milliseconds |Average |`IntegrationRuntimeName`, `DagFile`|PT1M |No|
|**Airflow Integration Runtime DAG Processing Last Run Seconds Ago**<p><p>Airflow Integration Runtime DAG Processing Last Run Seconds Ago |`AirflowIntegrationRuntimeDAGProcessingLastRunSecondsAgo` |Seconds |Average |`IntegrationRuntimeName`, `DagFile`|PT1M |No|
|**Airflow Integration Runtime DAG ProcessingManager Stalls**<p><p>Airflow Integration Runtime DAG ProcessingManager Stalls |`AirflowIntegrationRuntimeDAGProcessingManagerStalls` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime DAG Processing Processes**<p><p>Airflow Integration Runtime DAG Processing Processes |`AirflowIntegrationRuntimeDAGProcessingProcesses` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime DAG Processing Processor Timeouts**<p><p>Airflow Integration Runtime DAG Processing Processor Timeouts |`AirflowIntegrationRuntimeDAGProcessingProcessorTimeouts` |Seconds |Average |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime DAG Processing Total Parse Time**<p><p>Airflow Integration Runtime DAG Processing Total Parse Time |`AirflowIntegrationRuntimeDAGProcessingTotalParseTime` |Seconds |Average |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime DAG Run Dependency Check**<p><p>Airflow Integration Runtime DAG Run Dependency Check |`AirflowIntegrationRuntimeDAGRunDependencyCheck` |Milliseconds |Average |`IntegrationRuntimeName`, `DagId`|PT1M |No|
|**Airflow Integration Runtime DAG Run Duration Failed**<p><p>Airflow Integration Runtime DAG Run Duration Failed |`AirflowIntegrationRuntimeDAGRunDurationFailed` |Milliseconds |Average |`IntegrationRuntimeName`, `DagId`|PT1M |No|
|**Airflow Integration Runtime DAG Run Duration Success**<p><p>Airflow Integration Runtime DAG Run Duration Success |`AirflowIntegrationRuntimeDAGRunDurationSuccess` |Milliseconds |Average |`IntegrationRuntimeName`, `DagId`|PT1M |No|
|**Airflow Integration Runtime DAG Run First Task Scheduling Delay**<p><p>Airflow Integration Runtime DAG Run First Task Scheduling Delay |`AirflowIntegrationRuntimeDAGRunFirstTaskSchedulingDelay` |Milliseconds |Average |`IntegrationRuntimeName`, `DagId`|PT1M |No|
|**Airflow Integration Runtime DAG Run Schedule Delay**<p><p>Airflow Integration Runtime DAG Run Schedule Delay |`AirflowIntegrationRuntimeDAGRunScheduleDelay` |Milliseconds |Average |`IntegrationRuntimeName`, `DagId`|PT1M |No|
|**Airflow Integration Runtime Executor Open Slots**<p><p>Airflow Integration Runtime Executor Open Slots |`AirflowIntegrationRuntimeExecutorOpenSlots` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Executor Queued Tasks**<p><p>Airflow Integration Runtime Executor Queued Tasks |`AirflowIntegrationRuntimeExecutorQueuedTasks` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Executor Running Tasks**<p><p>Airflow Integration Runtime Executor Running Tasks |`AirflowIntegrationRuntimeExecutorRunningTasks` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Job End**<p><p>Airflow Integration Runtime Job End |`AirflowIntegrationRuntimeJobEnd` |Count |Total |`IntegrationRuntimeName`, `Job`|PT1M |No|
|**Airflow Integration Runtime Heartbeat Failure**<p><p>Airflow Integration Runtime Heartbeat Failure |`AirflowIntegrationRuntimeJobHeartbeatFailure` |Count |Total |`IntegrationRuntimeName`, `Job`|PT1M |No|
|**Airflow Integration Runtime Job Start**<p><p>Airflow Integration Runtime Job Start |`AirflowIntegrationRuntimeJobStart` |Count |Total |`IntegrationRuntimeName`, `Job`|PT1M |No|
|**Airflow Integration Runtime Memory Percentage**<p><p>Airflow Integration Runtime Memory Percentage |`AirflowIntegrationRuntimeMemoryPercentage` |Percent |Average |`IntegrationRuntimeName`, `ContainerName`|PT1M |Yes|
|**Airflow Integration Runtime Node Count**<p><p>Airflow Integration Runtime Node Count |`AirflowIntegrationRuntimeNodeCount` |Count |Average |`IntegrationRuntimeName`, `ComputeNodeSize`|PT1M |Yes|
|**Airflow Integration Runtime Operator Failures**<p><p>Airflow Integration Runtime Operator Failures |`AirflowIntegrationRuntimeOperatorFailures` |Count |Total |`IntegrationRuntimeName`, `Operator`|PT1M |No|
|**Airflow Integration Runtime Operator Successes**<p><p>Airflow Integration Runtime Operator Successes |`AirflowIntegrationRuntimeOperatorSuccesses` |Count |Total |`IntegrationRuntimeName`, `Operator`|PT1M |No|
|**Airflow Integration Runtime Pool Open Slots**<p><p>Airflow Integration Runtime Pool Open Slots |`AirflowIntegrationRuntimePoolOpenSlots` |Count |Total |`IntegrationRuntimeName`, `Pool`|PT1M |No|
|**Airflow Integration Runtime Pool Queued Slots**<p><p>Airflow Integration Runtime Pool Queued Slots |`AirflowIntegrationRuntimePoolQueuedSlots` |Count |Total |`IntegrationRuntimeName`, `Pool`|PT1M |No|
|**Airflow Integration Runtime Pool Running Slots**<p><p>Airflow Integration Runtime Pool Running Slots |`AirflowIntegrationRuntimePoolRunningSlots` |Count |Total |`IntegrationRuntimeName`, `Pool`|PT1M |No|
|**Airflow Integration Runtime Pool Starving Tasks**<p><p>Airflow Integration Runtime Pool Starving Tasks |`AirflowIntegrationRuntimePoolStarvingTasks` |Count |Total |`IntegrationRuntimeName`, `Pool`|PT1M |No|
|**Airflow Integration Runtime Scheduler Critical Section Busy**<p><p>Airflow Integration Runtime Scheduler Critical Section Busy |`AirflowIntegrationRuntimeSchedulerCriticalSectionBusy` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Scheduler Critical Section Duration**<p><p>Airflow Integration Runtime Scheduler Critical Section Duration |`AirflowIntegrationRuntimeSchedulerCriticalSectionDuration` |Milliseconds |Average |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Scheduler Failed SLA Email Attempts**<p><p>Airflow Integration Runtime Scheduler Failed SLA Email Attempts |`AirflowIntegrationRuntimeSchedulerFailedSLAEmailAttempts` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Scheduler Heartbeats**<p><p>Airflow Integration Runtime Scheduler Heartbeats |`AirflowIntegrationRuntimeSchedulerHeartbeat` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Scheduler Orphaned Tasks Adopted**<p><p>Airflow Integration Runtime Scheduler Orphaned Tasks Adopted |`AirflowIntegrationRuntimeSchedulerOrphanedTasksAdopted` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Scheduler Orphaned Tasks Cleared**<p><p>Airflow Integration Runtime Scheduler Orphaned Tasks Cleared |`AirflowIntegrationRuntimeSchedulerOrphanedTasksCleared` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Scheduler Tasks Executable**<p><p>Airflow Integration Runtime Scheduler Tasks Executable |`AirflowIntegrationRuntimeSchedulerTasksExecutable` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Scheduler Tasks Killed Externally**<p><p>Airflow Integration Runtime Scheduler Tasks Killed Externally |`AirflowIntegrationRuntimeSchedulerTasksKilledExternally` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Scheduler Tasks Running**<p><p>Airflow Integration Runtime Scheduler Tasks Running |`AirflowIntegrationRuntimeSchedulerTasksRunning` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Scheduler Tasks Starving**<p><p>Airflow Integration Runtime Scheduler Tasks Starving |`AirflowIntegrationRuntimeSchedulerTasksStarving` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Started Task Instances**<p><p>Airflow Integration Runtime Started Task Instances |`AirflowIntegrationRuntimeStartedTaskInstances` |Count |Total |`IntegrationRuntimeName`, `DagId`, `TaskId`|PT1M |No|
|**Airflow Integration Runtime Task Instance Created Using Operator**<p><p>Airflow Integration Runtime Task Instance Created Using Operator |`AirflowIntegrationRuntimeTaskInstanceCreatedUsingOperator` |Count |Total |`IntegrationRuntimeName`, `Operator`|PT1M |No|
|**Airflow Integration Runtime Task Instance Duration**<p><p>Airflow Integration Runtime Task Instance Duration |`AirflowIntegrationRuntimeTaskInstanceDuration` |Milliseconds |Average |`IntegrationRuntimeName`, `DagId`, `TaskID`|PT1M |No|
|**Airflow Integration Runtime Task Instance Failures**<p><p>Airflow Integration Runtime Task Instance Failures |`AirflowIntegrationRuntimeTaskInstanceFailures` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Task Instance Finished**<p><p>Airflow Integration Runtime Task Instance Finished |`AirflowIntegrationRuntimeTaskInstanceFinished` |Count |Total |`IntegrationRuntimeName`, `DagId`, `TaskId`, `State`|PT1M |No|
|**Airflow Integration Runtime Task Instance Previously Succeeded**<p><p>Airflow Integration Runtime Task Instance Previously Succeeded |`AirflowIntegrationRuntimeTaskInstancePreviouslySucceeded` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Task Instance Successes**<p><p>Airflow Integration Runtime Task Instance Successes |`AirflowIntegrationRuntimeTaskInstanceSuccesses` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Task Removed From DAG**<p><p>Airflow Integration Runtime Task Removed From DAG |`AirflowIntegrationRuntimeTaskRemovedFromDAG` |Count |Total |`IntegrationRuntimeName`, `DagId`|PT1M |No|
|**Airflow Integration Runtime Task Restored To DAG**<p><p>Airflow Integration Runtime Task Restored To DAG |`AirflowIntegrationRuntimeTaskRestoredToDAG` |Count |Total |`IntegrationRuntimeName`, `DagId`|PT1M |No|
|**Airflow Integration Runtime Triggers Blocked Main Thread**<p><p>Airflow Integration Runtime Triggers Blocked Main Thread |`AirflowIntegrationRuntimeTriggersBlockedMainThread` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Triggers Failed**<p><p>Airflow Integration Runtime Triggers Failed |`AirflowIntegrationRuntimeTriggersFailed` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Triggers Running**<p><p>Airflow Integration Runtime Triggers Running |`AirflowIntegrationRuntimeTriggersRunning` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Triggers Succeeded**<p><p>Airflow Integration Runtime Triggers Succeeded |`AirflowIntegrationRuntimeTriggersSucceeded` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Airflow Integration Runtime Zombie Tasks Killed**<p><p>Airflow Integration Runtime Zombie Tasks Killed |`AirflowIntegrationRuntimeZombiesKilled` |Count |Total |`IntegrationRuntimeName`|PT1M |No|
|**Total factory size (GB unit)**<p><p>Total factory size (GB unit) |`FactorySizeInGbUnits` |Count |Maximum |\<none\>|PT1M |Yes|
|**Integration runtime available memory**<p><p>Integration runtime available memory |`IntegrationRuntimeAvailableMemory` |Bytes |Average |`IntegrationRuntimeName`, `NodeName`|PT1M |Yes|
|**Integration runtime available node count**<p><p>Integration runtime available node count |`IntegrationRuntimeAvailableNodeNumber` |Count |Average |`IntegrationRuntimeName`|PT1M |Yes|
|**Integration runtime queue duration**<p><p>Integration runtime queue duration |`IntegrationRuntimeAverageTaskPickupDelay` |Seconds |Average |`IntegrationRuntimeName`|PT1M |Yes|
|**Integration runtime CPU utilization**<p><p>Integration runtime CPU utilization |`IntegrationRuntimeCpuPercentage` |Percent |Average |`IntegrationRuntimeName`, `NodeName`|PT1M |Yes|
|**Integration runtime queue length**<p><p>Integration runtime queue length |`IntegrationRuntimeQueueLength` |Count |Average |`IntegrationRuntimeName`|PT1M |Yes|
|**Maximum allowed factory size (GB unit)**<p><p>Maximum allowed factory size (GB unit) |`MaxAllowedFactorySizeInGbUnits` |Count |Maximum |\<none\>|PT1M |Yes|
|**Maximum allowed entities count**<p><p>Maximum allowed entities count |`MaxAllowedResourceCount` |Count |Maximum |\<none\>|PT1M |Yes|
|**Copy available capacity percentage of MVNet integration runtime**<p><p>Copy available capacity percentage of MVNet integration runtime |`MVNetIRCopyAvailableCapacityPCT` |Percent |Maximum |`IntegrationRuntimeName`|PT1M |Yes|
|**Copy capacity utilization of MVNet integration runtime**<p><p>Copy capacity utilization of MVNet integration runtime |`MVNetIRCopyCapacityUtilization` |Percent |Maximum |`IntegrationRuntimeName`|PT1M |Yes|
|**Copy waiting queue length of MVNet integration runtime**<p><p>Copy waiting queue length of MVNet integration runtime |`MVNetIRCopyWaitingQueueLength` |Count |Average |`IntegrationRuntimeName`|PT1M |Yes|
|**External available capacity percentage of MVNet integration runtime**<p><p>External available capacity percentage of MVNet integration runtime |`MVNetIRExternalAvailableCapacityPCT` |Percent |Maximum |`IntegrationRuntimeName`|PT1M |Yes|
|**External capacity utilization of MVNet integration runtime**<p><p>External capacity utilization of MVNet integration runtime |`MVNetIRExternalCapacityUtilization` |Percent |Maximum |`IntegrationRuntimeName`|PT1M |Yes|
|**External waiting queue length of MVNet integration runtime**<p><p>External waiting queue length of MVNet integration runtime |`MVNetIRExternalWaitingQueueLength` |Count |Average |`IntegrationRuntimeName`|PT1M |Yes|
|**Pipeline available capacity percentage of MVNet integration runtime**<p><p>Pipeline available capacity percentage of MVNet integration runtime |`MVNetIRPipelineAvailableCapacityPCT` |Percent |Maximum |`IntegrationRuntimeName`|PT1M |Yes|
|**Pipeline capacity utilization of MVNet integration runtime**<p><p>Pipeline capacity utilization of MVNet integration runtime |`MVNetIRPipelineCapacityUtilization` |Percent |Maximum |`IntegrationRuntimeName`|PT1M |Yes|
|**Pipeline waiting queue length of MVNet integration runtime**<p><p>Pipeline waiting queue length of MVNet integration runtime |`MVNetIRPipelineWaitingQueueLength` |Count |Average |`IntegrationRuntimeName`|PT1M |Yes|
|**Cancelled pipeline runs metrics**<p><p>Cancelled pipeline runs metrics |`PipelineCancelledRuns` |Count |Total |`FailureType`, `CancelledBy`, `Name`|PT1M |Yes|
|**Elapsed Time Pipeline Runs Metrics**<p><p>Elapsed Time Pipeline Runs Metrics |`PipelineElapsedTimeRuns` |Count |Total |`RunId`, `Name`|PT1M |Yes|
|**Failed pipeline runs metrics**<p><p>Failed pipeline runs metrics |`PipelineFailedRuns` |Count |Total |`FailureType`, `Name`|PT1M |Yes|
|**Succeeded pipeline runs metrics**<p><p>Succeeded pipeline runs metrics |`PipelineSucceededRuns` |Count |Total |`FailureType`, `Name`|PT1M |Yes|
|**Total entities count**<p><p>Total entities count |`ResourceCount` |Count |Maximum |\<none\>|PT1M |Yes|
|**Cancelled SSIS integration runtime start metrics**<p><p>Cancelled SSIS integration runtime start metrics |`SSISIntegrationRuntimeStartCancel` |Count |Total |`IntegrationRuntimeName`|PT1M |Yes|
|**Failed SSIS integration runtime start metrics**<p><p>Failed SSIS integration runtime start metrics |`SSISIntegrationRuntimeStartFailed` |Count |Total |`IntegrationRuntimeName`|PT1M |Yes|
|**Succeeded SSIS integration runtime start metrics**<p><p>Succeeded SSIS integration runtime start metrics |`SSISIntegrationRuntimeStartSucceeded` |Count |Total |`IntegrationRuntimeName`|PT1M |Yes|
|**Stuck SSIS integration runtime stop metrics**<p><p>Stuck SSIS integration runtime stop metrics |`SSISIntegrationRuntimeStopStuck` |Count |Total |`IntegrationRuntimeName`|PT1M |Yes|
|**Succeeded SSIS integration runtime stop metrics**<p><p>Succeeded SSIS integration runtime stop metrics |`SSISIntegrationRuntimeStopSucceeded` |Count |Total |`IntegrationRuntimeName`|PT1M |Yes|
|**Cancelled SSIS package execution metrics**<p><p>Cancelled SSIS package execution metrics |`SSISPackageExecutionCancel` |Count |Total |`IntegrationRuntimeName`|PT1M |Yes|
|**Failed SSIS package execution metrics**<p><p>Failed SSIS package execution metrics |`SSISPackageExecutionFailed` |Count |Total |`IntegrationRuntimeName`|PT1M |Yes|
|**Succeeded SSIS package execution metrics**<p><p>Succeeded SSIS package execution metrics |`SSISPackageExecutionSucceeded` |Count |Total |`IntegrationRuntimeName`|PT1M |Yes|
|**Cancelled trigger runs metrics**<p><p>Cancelled trigger runs metrics |`TriggerCancelledRuns` |Count |Total |`Name`, `FailureType`|PT1M |Yes|
|**Failed trigger runs metrics**<p><p>Failed trigger runs metrics |`TriggerFailedRuns` |Count |Total |`Name`, `FailureType`|PT1M |Yes|
|**Succeeded trigger runs metrics**<p><p>Succeeded trigger runs metrics |`TriggerSucceededRuns` |Count |Total |`Name`, `FailureType`|PT1M |Yes|