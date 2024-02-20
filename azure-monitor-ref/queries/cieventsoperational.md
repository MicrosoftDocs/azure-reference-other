---
title: Example log table queries for CIEventsOperational
description:  Example queries for CIEventsOperational log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the CIEventsOperational table


### CIEventsOperational - event type ApiEvent  


Gets a list of operational events with eventType as APIEvent.  

```query
CIEventsOperational
| where EventType has "ApiEvent"
| sort by TimeGenerated desc
| limit 100 // You can adjust the limit value to the number of logs you would like to retrieve.
```



### CIEventsOperational- event type WorkflowEvent  


Gets a list of operational events with eventType as WorkflowEvent.  

```query
CIEventsOperational
| where EventType has "WorkflowEvent"
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



### CIEventsOperational - all events for a specific instance ID  


Gets a list of API events requests for a specific instance ID.  

```query
CIEventsOperational
| where InstanceId == "" // Add your InstanceId in the quotation marks
| sort by TimeGenerated desc
| limit 100
```

