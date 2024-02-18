---
title: Example log table queries for AegDeliveryFailureLogs
description:  Example queries for AegDeliveryFailureLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AegDeliveryFailureLogs table


### Delivery failures by topic and error  


Delivery failures logs by topic name and error message.  

```query
AegDeliveryFailureLogs 
| parse Message with * ", httpStatusCode=" HttpStatusCode "," * "., errorMessage=" ErrorMessage "," *
| parse _ResourceId with * "/topics/" TopicName 
| summarize by _ResourceId, TopicName, ErrorMessage
```



### Delivery failures by topic and error  


Delivery failures logs by topic name and error message.  

```query
// To create an alert for this query, click '+ New alert rule'
AegDeliveryFailureLogs 
| parse Message with * ", httpStatusCode=" HttpStatusCode "," * "., errorMessage=" ErrorMessage "," *
| parse _ResourceId with * "/topics/" TopicName 
| summarize by _ResourceId, TopicName, ErrorMessage
```



### Delivery failures by domain and error  


Delivery failures logs by domain name and error message.  

```query
// To create an alert for this query, click '+ New alert rule'
AegDeliveryFailureLogs 
| parse Message with * ", httpStatusCode=" HttpStatusCode "," * "., errorMessage=" ErrorMessage "," *
| parse _ResourceId with * "/domains/" DomainName 
| project TimeGenerated, _ResourceId, DomainName, TenantId, EventSubscriptionName, SubResourceName, OperationName, HttpStatusCode, ErrorMessage
| summarize by _ResourceId, DomainName, SubResourceName, EventSubscriptionName, ErrorMessage
```



### Topics Average Delivery Latency  


Average Delivery Latency summarized by Topics, Event Subscriptions.  

```query
AegDeliveryFailureLogs
| parse _ResourceId with * "/topics/" TopicName
| where TopicName!= "" // and TopicName == "YOUR_TOPIC_NAME"
| parse Message with * ", latencyInMs=" LatencyInMilliSecond "," *
| summarize AverageDeliveryLatencyInMs = avg(todouble(LatencyInMilliSecond)) by TopicName, EventSubscriptionName
// Uncomment to filter for a specific Topic Name
```



### Domains Average Delivery Latency   


Average Delivery Latency summarized by Domains, Event Subscriptions and SubResourceName.  

```query
AegDeliveryFailureLogs
| parse _ResourceId with * "/domains/" DomainName
| where DomainName != "" // and DomainName == "YOUR_DOMAIN_NAME"
| parse Message with * ", latencyInMs=" LatencyInMilliSecond "," *
| summarize AverageDeliveryLatencyInMs = avg(todouble(LatencyInMilliSecond)) by DomainName, EventSubscriptionName, SubResourceName
// Uncomment to filter by a specific Domain Name
```

