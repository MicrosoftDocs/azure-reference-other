---
title: Example log table queries for VIAudit
description:  Example queries for VIAudit log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the VIAudit table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Video Indexer Audit by account id  


Display audit events for account (AccountId = \<Guid ID\>), with an optional filter by user UPN.  

```query
VIAudit
| where AccountId == "<AccountId>"  // please fill in the accountId <Guid>
// | where Upn == "<Upn>" // to to filter on a specific user upn, uncomment this line
| limit 100
```



### Video Indexer Audit top 10 users by operations  


Render timechart of top 10 users by operations, with an optional account id for filtering.  

```query
// Trend of top 10 active Upn's
VIAudit
// | where AccountId == "<AccountId>"  // to filter on a specific accountId, uncomment this line
| where TimeGenerated > ago(30d)
| summarize count() by Upn
| top 10 by count_ desc
| project Upn
| join (VIAudit
| where TimeGenerated > ago(30d)
| summarize count() by Upn, bin(TimeGenerated,1d)) on Upn
| project TimeGenerated, Upn, count_
| render timechart
```



### Video Indexer Audit parsed error message  


Display audit failed events with an optional account id for filtering.  

```query
// Project failures with detailed error message.
VIAudit
// | where AccountId == "<AccountId>"  // to filter on a specific accountId, uncomment this line
| where  Status == "Failure"
| parse Description with "ErrorType: " ErrorType ". Message: " ErrorMessage ". Trace" *
| project TimeGenerated, OperationName, ErrorMessage, ErrorType, CorrelationId, _ResourceId
```



### Video Indexer Audit failed operations  


Display audit logs of all failed operations attempts, with an optional filter by account id and user UPN.  

```query
VIAudit
// | where AccountId == "<AccountId>"  // to filter on a specific accountId, uncomment this line
// | where Upn == "<Upn>" // to to filter on a specific user upn, uncomment this line
| where Status == "Failure"
| limit 100
```

