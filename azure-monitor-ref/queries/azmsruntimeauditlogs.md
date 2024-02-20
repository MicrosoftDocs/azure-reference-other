---
title: Example log table queries for AZMSRunTimeAuditLogs
description:  Example queries for AZMSRunTimeAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AZMSRunTimeAuditLogs table


### Publish successful connection for AMQP protocol  


Publish runtime successful connection for Advanced Message Queuing Protocol(AMQP).  

```query
AZMSRunTimeAuditLogs
| where Provider =~ "EventHub"
| where Protocol == "AMQP" and Status == "Success"
| project  ActivityName, Protocol, NetworkType, ClientIp, _ResourceId
| summarize by ActivityName
```



### Publish failed AAD logs  


Publish the failed entries for AAD auth.  

```query
AZMSRunTimeAuditLogs 
| extend NamespaceInfo = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "EventHub"
| where isnotnull(NamespaceInfo) and isnotnull(AuthKey) and AuthType == "AAD" and Status != "Success" 
| project NamespaceInfo, AuthKey, ActivityName, Protocol, NetworkType, ClientIp, _ResourceId
| summarize by NamespaceInfo, AuthKey, ActivityName
```



### Publish failed SAS logs  


Publish the failed entries for SAS auth.  

```query
AZMSRunTimeAuditLogs 
| extend NamespaceInfo = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "EventHub"
| where isnotnull(NamespaceInfo) and isnotnull(AuthKey) and AuthType == "SAS" and Status != "Success" 
| project NamespaceInfo, AuthKey, ActivityName, Protocol, NetworkType, ClientIp, _ResourceId
| summarize by NamespaceInfo, AuthKey, ActivityName
```



### Publish failure for send message  


Publish the runtime failure for send message event.  

```query
AZMSRunTimeAuditLogs 
| extend NamespaceInfo = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "EventHub"
| where isnotnull(NamespaceInfo) and Status != "Success" and ActivityName == "SendMessage"
| project NamespaceInfo, ActivityName, Protocol, NetworkType, ClientIp, _ResourceId
| summarize by NamespaceInfo, ActivityName
```



### Publish failure for Namespace  


Publish the runtime failure for multiple namespaces.  

```query
AZMSRunTimeAuditLogs 
| extend NamespaceInfo = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "EventHub"
| where isnotnull(NamespaceInfo) and Status != "Success"
| project NamespaceInfo, ActivityName, Protocol, NetworkType, ClientIp, _ResourceId
| summarize by NamespaceInfo, ActivityName
```



### [Classic] Errors in the last 7 days  


This lists all the errors for the last 7 days.  

```query
AzureDiagnostics
| where ResourceProvider ==\"MICROSOFT.EVENTHUB\"
| where Category == \"OperationalLogs\"
| summarize count() by \"EventName\", _ResourceId
```



### Publish successful connection for AMQP protocol  


Publish runtime successful connection for Advanced Message Queuing Protocol(AMQP).  

```query
AZMSRunTimeAuditLogs
| where Provider =~ "ServiceBus" 
| where Protocol == "AMQP" and Status == "Success"
| project  ActivityName, Protocol, NetworkType, ClientIp, _ResourceId
| summarize by ActivityName
```



### Publish failures for send message  


Publish the runtime failures for send message event.  

```query
AZMSRunTimeAuditLogs
| extend NamespaceInfo = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "ServiceBus"
| where isnotnull(NamespaceInfo) and Status != "Success" and ActivityName == "SendMessage"
| project NamespaceInfo, ActivityName, Protocol, NetworkType, ClientIp, _ResourceId
| summarize by NamespaceInfo, ActivityName
```



### Publish failure for namespace  


Publish the runtime failure for multiple namespaces.  

```query
AZMSRunTimeAuditLogs
| extend NamespaceInfo = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "ServiceBus"
| where isnotnull(NamespaceInfo) and Status != "Success"
| project NamespaceInfo, ActivityName, Protocol, NetworkType, ClientIp, _ResourceId
| summarize by NamespaceInfo, ActivityName
```



### Publish failed AAD logs  


Publish the failed entries for AAD authorization.  

```query
AZMSRunTimeAuditLogs
| extend NamespaceInfo = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "ServiceBus"
| where isnotnull(NamespaceInfo) and isnotnull(AuthKey) and AuthType == "AAD" and Status != "Success" 
| project NamespaceInfo, AuthKey, ActivityName, Protocol, NetworkType, ClientIp, _ResourceId
| summarize by NamespaceInfo, AuthKey, ActivityName
```



### Publish failed SAS logs  


Publish the failed entries for SAS authorization.  

```query
AZMSRunTimeAuditLogs
| extend NamespaceInfo = tostring(split(_ResourceId, "/")[8])
| where Provider =~ "ServiceBus"
| where isnotnull(NamespaceInfo) and isnotnull(AuthKey) and AuthType == "SAS" and Status != "Success" 
| project NamespaceInfo, AuthKey, ActivityName, Protocol, NetworkType, ClientIp, _ResourceId
| summarize by NamespaceInfo, AuthKey, ActivityName
```

