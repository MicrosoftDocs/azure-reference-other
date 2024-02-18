---
title: Example log table queries for TSIIngress
description:  Example queries for TSIIngress log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the TSIIngress table


### Show event source connection errors  


Retrieves the most recent 100 logs pertaining to event source connection failures and summarizes them to display the time when the log was generated (TimeGenerated), a high level description (ResultDescription), a message continaing details on what went wrong and how to fix it (Message), and your event source's current configuration (EventSourceProperties).  

```query
//Retrieves the most recent 100 logs pertaining to event source connection failures and summarizes them to display the time when the log was generated (TimeGenerated), a high level description (ResultDescription), a message continaing details on what went wrong and how to fix it (Message), and your event source's current configuration (EventSourceProperties). 
TSIIngress
| where OperationName == 'Microsoft.TimeSeriesInsights/environments/eventsources/ingress/connect'
| project TimeGenerated, ResultDescription, Message, tostring(EventSourceProperties)
| top 100 by TimeGenerated desc
```



### 10 latest Ingress logs  


Shows the most recent ten error logs in the Ingress category. This is helpful when getting familiar with the TSIIngress schema.  

```query
//Retrieves the most recent ten error logs in the Ingress category. This is helpful when getting familiar with the TSIIngress schema.
TSIIngress
| top 10 by TimeGenerated
```



### Show deserialization errors  


Retrieves the most recent 100 error logs from failures to deserialize telemetry message(s) and summarizes them to display the time when the log was generated (TimeGenerated), a high level description (ResultDescription), and a message with the deserialization error (Message).  

```query
//Retrieves the most recent 100 error logs from failures to deserialize telemetry message(s) and summarizes them to display the time when the log was generated (TimeGenerated), a high level description (ResultDescription), and a message with the deserialization error (Message).
TSIIngress
| where OperationName == 'Microsoft.TimeSeriesInsights/environments/eventsources/ingress/deserialize'
| project TimeGenerated, ResultDescription, Message, tostring(EventSourceProperties)
| top 100 by TimeGenerated desc
```

