---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Synapse/workspaces/scopePools, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|PN duration of SCOPE job<p><p>PN (process node) duration (Milliseconds) used by each SCOPE job |`ScopePoolJobPNMetric` |Milliseconds |Maximum, Minimum, Average, Total, Count |JobType, JobResult|PT1M |Yes|
|Queued duration of SCOPE job<p><p>Queued duration (Milliseconds) used by each SCOPE job |`ScopePoolJobQueuedDurationMetric` |Milliseconds |Maximum, Minimum, Average, Total, Count |JobType|PT1M |Yes|
|Running duration of SCOPE job<p><p>Running duration (Milliseconds) used by each SCOPE job |`ScopePoolJobRunningDurationMetric` |Milliseconds |Maximum, Minimum, Average, Total, Count |JobType, JobResult|PT1M |Yes|