---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Sql/servers/jobAgents, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Elastic Jobs Executions Failed<p><p>Number of job executions that failed while trying to execute on target |`elastic_jobs_failed` |Count |Total, Count |No Dimensions|PT1M |Yes|
|Elastic Jobs Executions Successful<p><p>Number of job executions that were able to successfully execute on target |`elastic_jobs_successful` |Count |Total, Count |No Dimensions|PT1M |Yes|
|Elastic Jobs Executions Timed Out<p><p>Number of job executions that expired before execution was able to finish on target. |`elastic_jobs_timeout` |Count |Total, Count |No Dimensions|PT1M |Yes|