---
title: Example log table queries for ContainerLog
description:  Example queries for ContainerLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ContainerLog table


### Find a value in Container Logs Table  


** This query requires a parameter to run. Container Logs table is used Log lines collected from stdout and stderr streams for containers. This query will find rows in the ContainerLogs table where LogEntry has specified String.  

```query
//This qeury requires a parameter to work.
//The ContainerLog table holds Log lines collected from stdout and stderr streams for containers.
//Note: the query runs by default for the last 24 hours. Use the time pikcer to adjust time span for query
let FindString = "";//Please update term  you would like to find in LogEntry here
ContainerLog 
| where LogEntry has FindString 
|take 100
```



### Billable Log Data by log-type  


See container logs billable data for the last 7d ,segregated by log-type.  

```query
// Set the requested time, anytime greater than 15d can take longer
let billableTimeView = 7d;  
//Join ContainerLog on KubePodInventory for LogEntry source
ContainerLog
| join(KubePodInventory | where TimeGenerated > startofday(ago(billableTimeView)))on ContainerID
| where TimeGenerated > startofday(ago(billableTimeView))
| summarize Total=sum(_BilledSize)/ 1000 by bin(TimeGenerated, 1d), LogEntrySource
```



### List container logs per namespace  


View container logs from all the namespaces in the cluster.  

```query
ContainerLog
|where TimeGenerated > startofday(ago(1h))
|join(
KubePodInventory
| where TimeGenerated > startofday(ago(1h)) 
| distinct Computer, ContainerID, Namespace
)//KubePodInventory Contains namespace information
on Computer, ContainerID
| project TimeGenerated, ContainerID, Namespace , LogEntrySource , LogEntry
```



### Find In ContainerLog  


Find in ContainerLog to search for a specific value in the ContainerLog table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
ContainerLog
| where * contains tostring(SearchValue)
| take 1000
```

