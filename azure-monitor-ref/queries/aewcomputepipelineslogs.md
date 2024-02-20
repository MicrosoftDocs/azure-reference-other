---
title: Example log table queries for AEWComputePipelinesLogs
description:  Example queries for AEWComputePipelinesLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AEWComputePipelinesLogs table


### AEWComputePipelinesLogs get daily tasks count  


Get daily tasks count from compute pipelines records in selected time range.  

```query
AEWComputePipelinesLogs
| where EventName =~ "ScorecardRequestSucceeded" or EventName =~ "ScorecardRequestFailed"
| where Properties.ExperimentationGroup =~ "test~ExperimentationGroup"
| summarize Count = count() by Date = bin(TimeGenerated, 1d), ExperimentationGroup = tostring(Properties.ExperimentationGroup)
| sort by Date
```



### AEWComputePipelinesLogs get failed tasks detail  


Get latest 100 failed tasks detail from compute pipelines records in selected time range.  

```query
AEWComputePipelinesLogs
| where EventName =~ "ScorecardRequestFailed"
| where Properties.ExperimentationGroup =~ "test~ExperimentationGroup"
| project
    TimeGenerated
    ,EventName
    ,ExperimentationGroup = Properties.ExperimentationGroup
    ,AnalysisType = Properties.AnalysisType
| sort by TimeGenerated desc
| take 100
```



### AEWComputePipelinesLogs get long running jobs  


Get long running jobs from compute pipelines records in last seven days.  

```query
AEWComputePipelinesLogs
| where EventName =~ "CosmosJobUtilization"
| where Properties.ExperimentationGroup =~ "test~ExperimentationGroup"
| where todouble(Properties.JobRunningInSeconds) >= 24 * 60 * 60
| project
    TimeGenerated
    ,EventName
    ,ExperimentationGroup = Properties.ExperimentationGroup
    ,AnalysisType = Properties.AnalysisType
| sort by TimeGenerated desc

```



### AEWComputePipelinesLogs get task E2E latency time  


Get task E2E latency time of compute pipelines records in selected time range.  

```query
AEWComputePipelinesLogs
| where EventName =~ "ScorecardRequestSucceeded" or EventName =~ "ScorecardRequestFailed"
| where Properties.ExperimentationGroup =~ "test~ExperimentationGroup"
| summarize
  ScorecardRequestTimeInHoursP99 = percentile(todouble(Properties.ScorecardProcessingInSeconds) / 60 / 60, 99)
  ,ScorecardRequestTimeInHoursAvg = avg(todouble(Properties.ScorecardProcessingInSeconds) / 60 / 60)
  by Date = bin(TimeGenerated, 1d), ExperimentationGroup = tostring(Properties.ExperimentationGroup)
| sort by Date, ExperimentationGroup
```

