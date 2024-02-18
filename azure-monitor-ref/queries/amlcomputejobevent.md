---
title: Example log table queries for AmlComputeJobEvent
description:  Example queries for AmlComputeJobEvent log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlComputeJobEvent table


### Get failed jobs  


Get top 100 failed jobs.  

```query
AmlComputeJobEvent
| where EventType == "JobFailed"
| project  TimeGenerated, ClusterId, EventType, ExecutionState, ToolType, JobErrorMessage, ErrorDetails
| limit 100
```



### Get records for a job  


Get top 100 records for a specific job name.  

```query
AmlComputeJobEvent
| where JobName == "automl_a9940991-dedb-4262-9763-2fd08b79d8fb_setup"
| project  TimeGenerated, ClusterId, EventType, ExecutionState, ToolType
| limit 100
```



### Display top 5 longest job runs  


Display top 5 longest job runs.  

```query
AmlComputeJobEvent
| where OperationName == "JobSubmitted"
| join kind = inner (AmlComputeJobEvent
        | where OperationName == "JobSucceeded"
        | project StopTime=TimeGenerated, JobId)
    on JobId 
|project Duration=(StopTime-TimeGenerated), ExperimentName, WorkspaceName, ClusterName, JobName
|top 5 by Duration desc nulls last
```

