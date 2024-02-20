---
title: Example log table queries for VIIndexing
description:  Example queries for VIIndexing log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the VIIndexing table


### Failed Indexing operations  


Display Video Indexer Account logs of all failed indexing operations.  

```query
// Failed Indexing operations 
// Display Video Indexer Account logs of all failed indexing operations. 
VIIndexing
// | where AccountId == "<AccountId>"  // to filter on a specific accountId, uncomment this line
| where Status == "Failure"
| summarize count() by bin(TimeGenerated, 1d)
| render columnchart
```



### Top 10 users  


Summarize top 10 users.  

```query
// Video Indexer top 10 users by operations 
// Render timechart of top 10 users by operations, with an optional account id for filtering. 
// Trend of top 10 active Upn's
VIIndexing
// | where AccountId == "<AccountId>"  // to filter on a specific accountId, uncomment this line
| where OperationName in ("IndexingStarted", "ReindexingStarted")
| summarize count() by Upn
| top 10 by count_ desc
| project Upn
| join (VIIndexing
| where TimeGenerated > ago(30d)
| where OperationName in ("IndexingStarted", "ReindexingStarted")
| summarize count() by Upn, bin(TimeGenerated,1d)) on Upn
| project TimeGenerated, Upn, count_
| render timechart
```

