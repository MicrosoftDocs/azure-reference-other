---
title: Example log table queries for ACSCallAutomationIncomingOperations
description:  Example queries for ACSCallAutomationIncomingOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSCallAutomationIncomingOperations table


### Call Automation operations  


Returns all distinct combinations of call automation operation and version pairs.  

```query
ACSCallAutomationIncomingOperations
| distinct OperationName, OperationVersion 
| limit 100
```



### Calculate Call Automation operation duration percentiles  


Calculates the 90th, 95th, and 99th percentiles of run duration in milliseconds for each call automation operation. It can be customized to be run for a single operation, or for other percentiles.  

```query
ACSCallAutomationIncomingOperations
// where OperationName == "<operation>" // This can be uncommented and specified to calculate only a single operation's duration percentiles
| summarize percentiles(DurationMs, 90, 95, 99) by OperationName, OperationVersion // calculate 90th, 95th, and 99th percentiles of each Operation
| limit 100
```



### Top 5 IP addresses per Call Automation operation  


For every call automation operation, fetch the 5 IP addresses that have called that operation the most.  

```query
ACSCallAutomationIncomingOperations
// | where OperationName == "<operation>" // This can be uncommented and specified to calculate only a single operation's count
| top-nested of OperationName by dummy=max(0), // For all the Operations...
  top-nested 5 of CallerIpAddress by count() // List the IP address that have called that operation the most
| project-away dummy // Remove dummy line from the result set
| limit 100
```



### Call Automation operational errors  


List every call automation error ordered by recency.  

```query
ACSCallAutomationIncomingOperations
| where ResultType == "Failed"
| project TimeGenerated, OperationName, OperationVersion, ResultSignature
| order by TimeGenerated desc
| limit 100
```



### Call Automation operation result counts  


For every call automation operation, count the types of returned results.  

```query
ACSCallAutomationIncomingOperations
| summarize Count = count() by OperationName, ResultType //, ResultSignature // This can also be uncommented to determine the count of each ResultSignature for each ResultType 
| order by OperationName asc, Count desc
| limit 100
```



### Call Automation logs for call connection ID  


Queries Call Automation logs for a particular call connection ID.  

```query
ACSCallAutomationIncomingOperations
//| where CallConnectionId == "<callConnectionId>" // This can be uncommented to filter on a specific call connection ID
| limit 100

```



### Call Automation API operations on a call  


Returns all Call Automation API operation and version pairs for a specific call (correlation ID).  

```query
ACSCallAutomationIncomingOperations
//| where CorrelationId == "<correlation ID>" // This can be uncommented to filter on a specific correlation ID
| project CorrelationId, OperationName, OperationVersion
| limit 100
```



### CallDiagnostics log for CallAutomation API call  


Queries the diagnostics log for a call which was interacted with by Call Automation API using correlation ID.  

```query
ACSCallAutomationIncomingOperations 
//| where CorrelationId == "<correlation ID>" // This can be uncommented to filter on a specific correlation ID
| join kind=inner
    (ACSCallDiagnostics)
    on CorrelationId
| limit 100

```



### CallSummary log for CallAutomation API call  


Queries the summary log for a call which was interacted with by Call Automation API using correlation ID.  

```query
ACSCallAutomationIncomingOperations 
//| where CorrelationId == "<correlation ID>" // This can be uncommented to filter on a specific correlation ID
| join kind=inner
    (ACSCallSummary)
    on CorrelationId
| limit 100

```

