---
title: Example log table queries for ACSAuthIncomingOperations
description:  Example queries for ACSAuthIncomingOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSAuthIncomingOperations table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### List distinct auth operations  


Returns all distinct combinations of auth operation and version pairs.  

```query
ACSAuthIncomingOperations
| distinct OperationName, OperationVersion 
| limit 100
```



### Calculate auth operation duration percentiles  


Calculates the 90th, 95th, and 99th percentiles of run duration in milliseconds for each auth operation. It can be customized to be run for a single operation, or for other percentiles.  

```query
ACSAuthIncomingOperations
// where OperationName == "<operation>" // This can be uncommented and specified to calculate only a single operation's duration percentiles
| summarize percentiles(DurationMs, 90, 95, 99) by OperationName, OperationVersion // calculate 90th, 95th, and 99th percentiles of each Operation
| limit 100

```



### Top 5 IP addresses per auth operation  


For every auth operation, fetch the 5 IP addresses that have called that operation the most.  

```query
ACSAuthIncomingOperations
// | where OperationName == "<operation>" // This can be uncommented and specified to calculate only a single operation's count
| top-nested of OperationName by dummy=max(0), // For all the Operations...
  top-nested 5 of CallerIpAddress by count() // List the IP address that have called that operation the most
| project-away dummy // Remove dummy line from the result set
| limit 100
```



### Auth operational errors  


List every auth error ordered by recency.  

```query
ACSAuthIncomingOperations
| where ResultType == "Failed"
| project TimeGenerated, OperationName, OperationVersion, ResultSignature, ResultDescription
| order by TimeGenerated desc
| limit 100
```



### Auth operation result counts  


For every auth operation, count the types of returned results.  

```query
ACSAuthIncomingOperations
| summarize Count = count() by OperationName, ResultType //, ResultSignature // This can also be uncommented to determine the count of each ResultSignature for each ResultType 
| order by OperationName asc, Count desc
| limit 100
```

