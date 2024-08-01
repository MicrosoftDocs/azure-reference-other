---
title: Example log table queries for ACSNetworkTraversalDiagnostics
description:  Example queries for ACSNetworkTraversalDiagnostics log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSNetworkTraversalDiagnostics table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Network Traversal relay session data relayed per identity  


List the amount of data relayed (in bytes) for each Network Traversal relay session.  

```query
ACSNetworkTraversalDiagnostics
| where OperationName == "RelaySessionEnd"
| summarize by
    Identity,
    TotalBytesToClient,
    TotalBytesFromClient,
    TotalBytes = TotalBytesToClient + TotalBytesFromClient
| sort by TotalBytes desc
| limit 100
```



### Network Traversal relay session duration  


Calculate the duration of each Network Traversal relay session.  

```query
ACSNetworkTraversalDiagnostics
| where OperationName == "RelaySessionStart"
| extend StartTime = TimeGenerated
| join (
    ACSNetworkTraversalDiagnostics
    | where OperationName == "RelaySessionEnd"
    | extend EndTime = TimeGenerated
) on CorrelationId
| summarize by
    CorrelationId,
    SessionDurationMs = datetime_diff('millisecond', EndTime, StartTime)
| sort by SessionDurationMs desc
| limit 100
```



### Network Traversal relay session end reason  


Count the number of relay sessions that ended for each end reason.  

```query
ACSNetworkTraversalDiagnostics
| where OperationName == "RelaySessionEnd"
| summarize Count = count() by Reason
| sort by Count desc
```



### Network Traversal relay sessions per IP address  


Count the number of relay sessions started by each unique IP address.  

```query
ACSNetworkTraversalDiagnostics
| where OperationName == "RelaySessionStart" // Only RelaySessionStart has a caller IP address
| summarize Count = count() by CallerIpAddress
| limit 100
| order by Count desc
```



### Network Traversal relay session start errors  


List every Network Traversal relay session start error ordered by recency.  

```query
ACSNetworkTraversalDiagnostics
| where ResultType == "Failed"
| project TimeGenerated, OperationName, ResultSignature
| order by TimeGenerated desc
| limit 100
```

