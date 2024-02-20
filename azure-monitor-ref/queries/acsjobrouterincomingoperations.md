---
title: Example log table queries for ACSJobRouterIncomingOperations
description:  Example queries for ACSJobRouterIncomingOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSJobRouterIncomingOperations table


### Job Router operations  


Returns all distinct combinations of job router operation and version pairs.  

```query
ACSJobRouterIncomingOperations
| distinct OperationName, OperationVersion 
| limit 100
```



### Calculate Job Router operation duration percentiles  


Calculates the 90th, 95th, and 99th percentiles of run duration in milliseconds for each chat operation. It can be customized to be run for a single operation, or for other percentiles.  

```query
ACSJobRouterIncomingOperations
// where OperationName == "<operation>" // This can be uncommented and specified to calculate only a single operation's duration percentiles
| summarize percentiles(DurationMs, 90, 95, 99) by OperationName, OperationVersion // calculate 90th, 95th, and 99th percentiles of each Operation
| limit 100

```



### Top 5 IP addresses per Job Router operation  


For every job router operation, fetch the 5 IP addresses that have called that operation the most.  

```query
ACSJobRouterIncomingOperations
// | where OperationName == "<operation>" // This can be uncommented and specified to calculate only a single operation's count
| top-nested of OperationName by dummy=max(0), // For all the Operations...
  top-nested 5 of CallerIpAddress by count() // List the IP address that have called that operation the most
| project-away dummy // Remove dummy line from the result set
| limit 100
```



### Job Router operational errors  


List every job router error ordered by recency.  

```query
ACSJobRouterIncomingOperations
| where ResultType == "Failed"
| project TimeGenerated, OperationName, OperationVersion, ResultSignature, ResultDescription
| order by TimeGenerated desc
| limit 100
```



### Job Router operation result counts  


For every job router operation, count the types of returned results.  

```query
ACSJobRouterIncomingOperations
| summarize Count = count() by OperationName, OperationVersion, ResultType, SdkType, EntityType //, ResultSignature // This can also be uncommented to determine the count of each ResultSignature for each ResultType 
| order by OperationName asc, Count desc
| limit 100
```

