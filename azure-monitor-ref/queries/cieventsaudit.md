---
title: Example log table queries for CIEventsAudit
description:  Example queries for CIEventsAudit log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the CIEventsAudit table


### CIEventsAudit - API response codes line chart  


Line chart showing requests response duration per operation.  

```query
CIEventsAudit
| summarize DurationMs = avg(DurationMs)  by bin(TimeGenerated, 5m), OperationName
| render timechart
```



### CIEventsAudit - result type ClientError  


Gets a list of operational events request that finished with result type ClientError: HTTP status code < 500.  

```query
CIEventsAudit
| where ResultType has "ClientError"
| sort by TimeGenerated desc
| limit 100 // You can adjust the limit value to the number of logs you would like to retrieve.
```



### CIEventsAudit - security level Error  


Gets a list of API requests that finished with Error severity level.  

```query
CIEventsAudit
| where Level has "Error"
| sort by TimeGenerated desc
| limit 100 // You can adjust the limit value to the number of logs you would like to retrieve.
```



### CIEvents - all events for a specific correlation id  


Gets a list of all events request for a specific correlation id  

```query
union CIEventsAudit , CIEventsOperational
| where CorrelationId == "" // Add your CorrelationId in the quotation marks
| sort by TimeGenerated desc
| limit 100
```



### CIEventsAudit - all events for a specific instance ID  


Gets a list of API events requests for a specific instance ID.  

```query
CIEventsAudit
| where InstanceId == "" // Add your InstanceId in the quotation marks
| sort by TimeGenerated desc
| limit 100
```

