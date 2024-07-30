---
title: Example log table queries for ACSAdvancedMessagingOperations
description:  Example queries for ACSAdvancedMessagingOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSAdvancedMessagingOperations table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Advanced Messaging operations  


Returns all distinct combinations of Advanced Messaging operation and version pairs.  

```query
ACSAdvancedMessagingOperations
| distinct OperationName, OperationVersion 
| limit 100
```



### Advanced Messaging operation duration percentiles  


Calculates the 90th, 95th, and 99th percentiles of run duration in milliseconds for each chat operation. It can be customized to be run for a single operation, or for other percentiles.  

```query
ACSAdvancedMessagingOperations
// where OperationName == "<operation>" // This can be uncommented and specified to calculate only a single operation's duration percentiles
| summarize percentiles(DurationMs, 90, 95, 99) by OperationName, OperationVersion // calculate 90th, 95th, and 99th percentiles of each Operation
| limit 100

```



### Advanced Messaging top 5 IP addresses per operation  


For every Advanced Messaging operation, fetch the 5 IP addresses that have called that operation the most.  

```query
ACSAdvancedMessagingOperations
// | where OperationName == "<operation>" // This can be uncommented and specified to calculate only a single operation's count
| top-nested of OperationName by dummy=max(0), // For all the Operations...
  top-nested 5 of CallerIpAddress by count() // List the IP address that have called that operation the most
| project-away dummy // Remove dummy line from the result set
| limit 100
```



### Advanced Messaging operational errors  


List every Advanced Messaging error ordered by recency.  

```query
ACSAdvancedMessagingOperations
| where ResultType == "Failed"
| project TimeGenerated, OperationName, OperationVersion, ResultSignature, ResultDescription
| order by TimeGenerated desc
| limit 100
```



### Advanced Messaging operation result counts  


For every Advanced Messaging operation, count the types of returned results.  

```query
ACSAdvancedMessagingOperations
| summarize Count = count() by OperationName, OperationVersion, ResultType //, ResultSignature // This can also be uncommented to determine the count of each ResultSignature for each ResultType 
| order by OperationName asc, Count desc
| limit 100
```



### Advanced Messaging channel activity  


Summary of the message activity per channel for the past 24 hours.  

```query
ACSAdvancedMessagingOperations
| where TimeGenerated > ago(24h)
| summarize count() by ChannelId, MessageType
| order by ChannelId asc
```



### Advanced Messaging message status count  


Count of message status for the past 24 hours.  

```query
ACSAdvancedMessagingOperations
| where TimeGenerated > ago(24h)
| summarize Count = count() by MessageType, MessageStatus
| order by MessageType asc, Count desc
```

