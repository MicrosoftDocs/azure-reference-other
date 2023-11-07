---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Synapse/workspaces/scopePools, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**PN duration of SCOPE job**<p><p>PN (process node) duration (Milliseconds) used by each SCOPE job |`ScopePoolJobPNMetric` |Milliseconds |Maximum, Minimum, Average, Total, Count |`JobType`, `JobResult`|PT1M |Yes|
|**Queued duration of SCOPE job**<p><p>Queued duration (Milliseconds) used by each SCOPE job |`ScopePoolJobQueuedDurationMetric` |Milliseconds |Maximum, Minimum, Average, Total, Count |`JobType`|PT1M |Yes|
|**Running duration of SCOPE job**<p><p>Running duration (Milliseconds) used by each SCOPE job |`ScopePoolJobRunningDurationMetric` |Milliseconds |Maximum, Minimum, Average, Total, Count |`JobType`, `JobResult`|PT1M |Yes|