---
title: Example log table queries for AZMSVnetConnectionEvents
description:  Example queries for AZMSVnetConnectionEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AZMSVnetConnectionEvents table


### Publish deny connection by namespace  


Publish deny connection by namespace on network data.  

```query
AZMSVnetConnectionEvents
| extend NamespaceName = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "EventHub"
| where Action == "Deny Connection"
| project Action, _SubscriptionId, NamespaceName, AddressIp, Reason, Count
| summarize by Action, NamespaceName
```



### Publish namespace vnet data  


Publish vnet data for namespace by action status.  

```query
AZMSVnetConnectionEvents
| extend NamespaceName = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "EventHub"
| project Action, _SubscriptionId, NamespaceName, AddressIp, Reason, Count, _ResourceId
| summarize by NamespaceName, Action
```



### Publish deny connection by namespace  


Publish deny network connection information by namespace.  

```query
AZMSVNetConnectionEvents
| extend NamespaceName = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "Relay"
| where Action == "Deny Connection"
| project Action, _SubscriptionId, NamespaceName, AddressIp, Reason, Count
| summarize by Action, NamespaceName
```



### Publish virtual network events by namespace  


Publish virtual network events with outcome for namespace.  

```query
AZMSVNetConnectionEvents
| extend NamespaceName = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "Relay"
| project Action, _SubscriptionId, NamespaceName, AddressIp, Reason, Count, _ResourceId
| summarize by NamespaceName, Action
```



### Publish deny connection by namespace  


Publish deny network connection information by namespace.  

```query
AZMSVNetConnectionEvents
| extend NamespaceName = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "ServiceBus"
| where Action == "Deny Connection"
| project Action, _SubscriptionId, NamespaceName, AddressIp, Reason, Count
| summarize by Action, NamespaceName
```



### Publish virtual network events by namespace  


Publish virtual network events with outcome for namespace.  

```query
AZMSVNetConnectionEvents
| extend NamespaceName = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "ServiceBus"
| project Action, _SubscriptionId, NamespaceName, AddressIp, Reason, Count, _ResourceId
| summarize by NamespaceName, Action
```

