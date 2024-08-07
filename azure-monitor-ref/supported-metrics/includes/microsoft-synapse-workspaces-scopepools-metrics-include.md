---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Synapse/workspaces/scopePools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|SCOPE pool|**PN duration of SCOPE job**<br><br>PN (process node) duration (Milliseconds) used by each SCOPE job |`ScopePoolJobPNMetric` |Milliseconds |Maximum, Minimum, Average, Total, Count |`JobType`, `JobResult`|PT1M |Yes|
|SCOPE pool|**Queued duration of SCOPE job**<br><br>Queued duration (Milliseconds) used by each SCOPE job |`ScopePoolJobQueuedDurationMetric` |Milliseconds |Maximum, Minimum, Average, Total, Count |`JobType`|PT1M |Yes|
|SCOPE pool|**Running duration of SCOPE job**<br><br>Running duration (Milliseconds) used by each SCOPE job |`ScopePoolJobRunningDurationMetric` |Milliseconds |Maximum, Minimum, Average, Total, Count |`JobType`, `JobResult`|PT1M |Yes|