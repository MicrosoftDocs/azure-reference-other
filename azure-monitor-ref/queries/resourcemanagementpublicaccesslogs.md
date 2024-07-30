---
title: Example log table queries for ResourceManagementPublicAccessLogs
description:  Example queries for ResourceManagementPublicAccessLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ResourceManagementPublicAccessLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Group number of requests based on the IP address  


Get the number of request accessing the resource from an IP address.  

```query
//List the IP addresses and number of calls
ResourceManagementPublicAccessLogs
| where Category == "PublicAccessLogs"
| summarize count() by CallerIpAddress 
```



### Number of opertions triggered  


Count the number of request made.  

```query
// Count the number of operations.
ResourceManagementPublicAccessLogs
| where Category == "PublicAccessLogs"
| summarize count() by CorrelationId 
```



### Calls based on the target URI  


Chart the number of calls based on the target URI.  

```query
// Chart the number of calls based on the target URI.
ResourceManagementPublicAccessLogs
| where Category == "PublicAccessLogs"
| summarize count() by Uri, bin(TimeGenerated, 1m)
| render columnchart with (kind=stacked) 
```



### Calls based on operation name  


Count the number of request made based on operation name.  

```query
// List the operations and their number of calls from the public network
ResourceManagementPublicAccessLogs
| where Category == "PublicAccessLogs"
| summarize count() by OperationName
| order by count_
```



### Calls based on user  


Count the number of request made based on object identifiers.  

```query
// List the object identifiers and number of calls from each over the public network
ResourceManagementPublicAccessLogs
| where Category == "PublicAccessLogs"
| summarize count() by ObjectIdentifier
| order by count_ 
```

