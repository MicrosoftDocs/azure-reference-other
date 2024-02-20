---
title: Example log table queries for MicrosoftDataShareReceivedSnapshotLog
description:  Example queries for MicrosoftDataShareReceivedSnapshotLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the MicrosoftDataShareReceivedSnapshotLog table


### List received snapshots by duration  


A list of the snapshots sorted by duration time, over the last 7 days.  

```query
MicrosoftDataShareReceivedSnapshotLog
| where TimeGenerated > ago(7d)  
| where StartTime != "" and EndTime  != ""
| project StartTime , EndTime , DurationSeconds =(todatetime(EndTime)-todatetime(StartTime))/1s, ResourceName = split(_ResourceId,"/accounts/",1)// use split to get a part of the _ResourceId  
| sort by DurationSeconds desc nulls last
```



### Count failed received snapshots  


Count of failed snapshots over the last 7 days.  

```query
MicrosoftDataShareReceivedSnapshotLog
| where TimeGenerated > ago(7d)  
| where Status == "Failed" 
| summarize count() by _ResourceId 
```



### Frequent errors in received snapshots  


Top 10 most frequent errors over the last 7 days.  

```query
MicrosoftDataShareReceivedSnapshotLog 
| where TimeGenerated > ago(7d)  
| where Status == "Failed" 
| summarize count() by _ResourceId, DataSetType // Counting failed logs per datasettype
| top 10 by count_ desc nulls last
```



### Chart of daily received snapshots  


A time chart of the daily snapshots count, over the past week.  

```query
// Failed, In Progress and Succeeded Received Snapshots
MicrosoftDataShareReceivedSnapshotLog 
| where TimeGenerated > ago(7d)  
| summarize count() by bin(TimeGenerated, 1d), Status , _ResourceId // Aggregating by day //Click "Table" to see resource's name.
| render timechart
```

