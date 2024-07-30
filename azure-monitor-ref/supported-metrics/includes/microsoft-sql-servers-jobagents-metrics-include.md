---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Sql/servers/jobAgents, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Basic|**Elastic Jobs Executions Failed**<br><br>Number of job executions that failed while trying to execute on target |`elastic_jobs_failed` |Count |Total, Count |\<none\>|PT1M |Yes|
|Basic|**Elastic Jobs Executions Successful**<br><br>Number of job executions that were able to successfully execute on target |`elastic_jobs_successful` |Count |Total, Count |\<none\>|PT1M |Yes|
|Basic|**Elastic Jobs Executions Timed Out**<br><br>Number of job executions that expired before execution was able to finish on target. |`elastic_jobs_timeout` |Count |Total, Count |\<none\>|PT1M |Yes|