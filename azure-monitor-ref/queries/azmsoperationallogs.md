---
title: Example log table queries for AZMSOperationalLogs
description:  Example queries for AZMSOperationalLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AZMSOperationalLogs table


### Publish success data for topics  


Publish success data for topics for OperationLogs.  

```query
AZMSOperationalLogs
| extend TopicName = tostring(split(_ResourceId, "/")[10])
| where Provider =~ "EventHub"
| where isnotnull(TopicName) and Status == "Succeeded"
| project TopicName, _ResourceId, EventName, Status, Caller, _SubscriptionId
| summarize by TopicName, EventName
```



### Publish failures for subscription  


Publish management action failures for subscription.  

```query
AZMSOperationalLogs
| extend SubInfo = _SubscriptionId
| where Provider =~ "EventHub"
| where isnotnull(SubInfo) and Status != "Succeeded"
| project SubInfo, _ResourceId, EventName, Status, Caller
| summarize by SubInfo, EventName
```



### Publish failures for namespace  


Publish management action failures for namespace.  

```query
AZMSOperationalLogs
| extend NamespaceName = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "EventHub"
| where isnotnull(NamespaceName) and Status != "Succeeded"
| project NamespaceName, _ResourceId, EventName, Status, Caller, _SubscriptionId
| summarize by NamespaceName, EventName
```



### Publish success data for topics  


Publish success data for topics on CRUD Operations in Server Bus.  

```query
AZMSOperationalLogs
| extend TopicName = tostring(split(_ResourceId, "/")[10])
| where Provider =~ "ServiceBus"
| where isnotnull(TopicName) and Status == "Succeeded"
| project TopicName, _ResourceId, EventName, Status, Caller, _SubscriptionId
| summarize by TopicName, EventName
```



### Publish failures for Topics  


Publish management action failures for topics.  

```query
AZMSOperationalLogs
| extend TopicName = tostring(split(_ResourceId, "/")[10])
| where Provider =~ "ServiceBus"
| where isnotnull(TopicName) and Status != "Succeeded"
| project TopicName, _ResourceId, EventName, Status, Caller, SubscriptionId
| summarize by TopicName, EventName
```



### Publish failures for subscription  


Publish management action failures for subscription.  

```query
AZMSOperationalLogs
| extend SubInfo = _SubscriptionId
| where Provider =~ "ServiceBus"
| where isnotnull(SubInfo) and Status != "Succeeded"
| project SubInfo, _ResourceId, EventName, Status, Caller
| summarize by SubInfo, EventName
```



### Publish failures for namespace  


Publish management action failures for namespace.  

```query
AZMSOperationalLogs
| extend NamespaceName = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "ServiceBus"
| where isnotnull(NamespaceName) and Status != "Succeeded"
| project NamespaceName, _ResourceId, EventName, Status, Caller, _SubscriptionId
| summarize by NamespaceName, EventName
```

