---
title: Example log table queries for ACSNetworkTraversalIncomingOperations
description:  Example queries for ACSNetworkTraversalIncomingOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSNetworkTraversalIncomingOperations table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Distinct Network Traversal operations  


Returns all distinct combinations of Network Traversal operation and version pairs.  

```query
ACSNetworkTraversalIncomingOperations
| summarize Count = count() by OperationName, OperationVersion
| sort by Count desc
| limit 100
```



### Calculate Network Traversal operation duration percentiles  


Calculates the 90th, 95th, and 99th percentiles of run duration in milliseconds for each Network Traversal operation. It can be customized to be run for a single operation, or for other percentiles.  

```query
ACSNetworkTraversalIncomingOperations
// where OperationName == "<operation>" // This can be uncommented and specified to calculate only a single operation's duration percentiles
| summarize percentiles(DurationMs, 90, 95, 99) by OperationName, OperationVersion // calculate 90th, 95th, and 99th percentiles of each Operation
| limit 100

```



### Network Traversal operational errors  


List every Network Traversal error ordered by recency.  

```query
ACSNetworkTraversalIncomingOperations
| where ResultType == "Failed"
| project TimeGenerated, OperationName, OperationVersion, ResultSignature
| order by TimeGenerated desc
| limit 100
```



### Network Traversal operation result counts  


For every Network Traversal operation, count the types of returned results.  

```query
ACSNetworkTraversalIncomingOperations
| summarize Count = count() by OperationName, ResultType //, ResultSignature // This can also be uncommented to determine the count of each ResultSignature for each ResultType 
| order by OperationName asc, Count desc
| limit 100
```

