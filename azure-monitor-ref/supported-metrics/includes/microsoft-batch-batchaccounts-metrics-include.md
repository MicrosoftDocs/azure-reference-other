---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Batch/batchaccounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Dedicated Core Count**<br><br>Total number of dedicated cores in the batch account |`CoreCount` |Count |Total |\<none\>|PT1M |No|
|**Creating Node Count**<br><br>Number of nodes being created |`CreatingNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Idle Node Count**<br><br>Number of idle nodes |`IdleNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Job Delete Complete Events**<br><br>Total number of jobs that have been successfully deleted. |`JobDeleteCompleteEvent` |Count |Total |`jobId`|PT1M |Yes|
|**Job Delete Start Events**<br><br>Total number of jobs that have been requested to be deleted. |`JobDeleteStartEvent` |Count |Total |`jobId`|PT1M |Yes|
|**Job Disable Complete Events**<br><br>Total number of jobs that have been successfully disabled. |`JobDisableCompleteEvent` |Count |Total |`jobId`|PT1M |Yes|
|**Job Disable Start Events**<br><br>Total number of jobs that have been requested to be disabled. |`JobDisableStartEvent` |Count |Total |`jobId`|PT1M |Yes|
|**Job Start Events**<br><br>Total number of jobs that have been successfully started. |`JobStartEvent` |Count |Total |`jobId`|PT1M |Yes|
|**Job Terminate Complete Events**<br><br>Total number of jobs that have been successfully terminated. |`JobTerminateCompleteEvent` |Count |Total |`jobId`|PT1M |Yes|
|**Job Terminate Start Events**<br><br>Total number of jobs that have been requested to be terminated. |`JobTerminateStartEvent` |Count |Total |`jobId`|PT1M |Yes|
|**Leaving Pool Node Count**<br><br>Number of nodes leaving the Pool |`LeavingPoolNodeCount` |Count |Total |\<none\>|PT1M |No|
|**LowPriority Core Count**<br><br>Total number of low-priority cores in the batch account |`LowPriorityCoreCount` |Count |Total |\<none\>|PT1M |No|
|**Offline Node Count**<br><br>Number of offline nodes |`OfflineNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Pool Create Events**<br><br>Total number of pools that have been created |`PoolCreateEvent` |Count |Total |`poolId`|PT1M |Yes|
|**Pool Delete Complete Events**<br><br>Total number of pool deletes that have completed |`PoolDeleteCompleteEvent` |Count |Total |`poolId`|PT1M |Yes|
|**Pool Delete Start Events**<br><br>Total number of pool deletes that have started |`PoolDeleteStartEvent` |Count |Total |`poolId`|PT1M |Yes|
|**Pool Resize Complete Events**<br><br>Total number of pool resizes that have completed |`PoolResizeCompleteEvent` |Count |Total |`poolId`|PT1M |Yes|
|**Pool Resize Start Events**<br><br>Total number of pool resizes that have started |`PoolResizeStartEvent` |Count |Total |`poolId`|PT1M |Yes|
|**Preempted Node Count**<br><br>Number of preempted nodes |`PreemptedNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Rebooting Node Count**<br><br>Number of rebooting nodes |`RebootingNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Reimaging Node Count**<br><br>Number of reimaging nodes |`ReimagingNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Running Node Count**<br><br>Number of running nodes |`RunningNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Starting Node Count**<br><br>Number of nodes starting |`StartingNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Start Task Failed Node Count**<br><br>Number of nodes where the Start Task has failed |`StartTaskFailedNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Task Complete Events**<br><br>Total number of tasks that have completed |`TaskCompleteEvent` |Count |Total |`poolId`, `jobId`|PT1M |Yes|
|**Task Fail Events**<br><br>Total number of tasks that have completed in a failed state |`TaskFailEvent` |Count |Total |`poolId`, `jobId`|PT1M |Yes|
|**Task Start Events**<br><br>Total number of tasks that have started |`TaskStartEvent` |Count |Total |`poolId`, `jobId`|PT1M |Yes|
|**Low-Priority Node Count**<br><br>Total number of low-priority nodes in the batch account |`TotalLowPriorityNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Dedicated Node Count**<br><br>Total number of dedicated nodes in the batch account |`TotalNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Unusable Node Count**<br><br>Number of unusable nodes |`UnusableNodeCount` |Count |Total |\<none\>|PT1M |No|
|**Waiting For Start Task Node Count**<br><br>Number of nodes waiting for the Start Task to complete |`WaitingForStartTaskNodeCount` |Count |Total |\<none\>|PT1M |No|