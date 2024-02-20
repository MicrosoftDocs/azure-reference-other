---
title: Example log table queries for StorageBlobLogs
description:  Example queries for StorageBlobLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the StorageBlobLogs table


### Most common errors  


List 10 most common errors over the last 3 days.  

```query
StorageBlobLogs
| where TimeGenerated > ago(3d) and StatusText !contains "Success"
| summarize count() by StatusText
| top 10 by count_ desc
```



### Operations causing most errors  


List top 10 operations causing the most errors over the last 3 days.  

```query
StorageBlobLogs
| where TimeGenerated > ago(3d) and StatusText !contains "Success"
| summarize count() by OperationName
| top 10 by count_ desc
```



### Operations with the highest latency  


List top 10 operations with the longest end to end latency over the last 3 days.  

```query
StorageBlobLogs
| where TimeGenerated > ago(3d)
| top 10 by DurationMs desc
| project TimeGenerated, OperationName, DurationMs, ServerLatencyMs, ClientLatencyMs = DurationMs - ServerLatencyMs
```



### Operations causing server side throttling  


List all operations causing server side throttling errors over the last 3 days.  

```query
// To create an alert for this query, click '+ New alert rule'
StorageBlobLogs
| where TimeGenerated > ago(3d) and StatusText contains "ServerBusy"
| project TimeGenerated, OperationName, StatusCode, StatusText, _ResourceId
```



### Show anonymous requests  


List all requests with anonymous access over the last 3 days.  

```query
// To create an alert for this query, click '+ New alert rule'
StorageBlobLogs
| where TimeGenerated > ago(3d) and AuthenticationType == "Anonymous"
| project TimeGenerated, OperationName, AuthenticationType, Uri, _ResourceId
```



### Frequent operations chart  


A pie chart of operations used over the last 3 days.  

```query
StorageBlobLogs
| where TimeGenerated > ago(3d)
| summarize count() by OperationName
| sort by count_ desc 
| render piechart
```

