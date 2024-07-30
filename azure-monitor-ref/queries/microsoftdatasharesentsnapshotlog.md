---
title: Example log table queries for MicrosoftDataShareSentSnapshotLog
description:  Example queries for MicrosoftDataShareSentSnapshotLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the MicrosoftDataShareSentSnapshotLog table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### List sent snapshots by duration  


A list of the snapshots sorted by duration time over the last 7 days.  

```query
MicrosoftDataShareSentSnapshotLog
| where TimeGenerated > ago(7d) 
| where StartTime != "" and EndTime  != "" 
| project StartTime , EndTime , DurationSeconds =(todatetime(EndTime)-todatetime(StartTime))/1s , ResourceName = split(_ResourceId,"/accounts/",1) 
| sort by DurationSeconds desc nulls last 

```



### Count failed sent snapshots  


Total count of failed snapshots over the last 7 days.  

```query
MicrosoftDataShareSentSnapshotLog
| where TimeGenerated > ago(7d)  
| where Status == "Failed" 
| summarize count() by _ResourceId 
```



### Frequent errors in sent snapshots  


List top 10 errors over the last 7 days.  

```query
MicrosoftDataShareSentSnapshotLog 
| where TimeGenerated > ago(7d)  
| where Status == "Failed" 
| summarize count() by _ResourceId, DataSetType// Counting failed logs per datasettype
| top 10 by count_ desc nulls last
```



### Chart of daily sent snapshots  


A time chart of recent snapshots count, succeeded VS failed.  

```query
//Succeeded VS Failed
MicrosoftDataShareSentSnapshotLog 
| where TimeGenerated > ago(30d)  
| summarize count() by bin(TimeGenerated, 1d), Status, _ResourceId // Aggregating by day //Click "Table" to see resource's name.
| render timechart
```

