---
title: Example log table queries for SignalRServiceDiagnosticLogs
description:  Example queries for SignalRServiceDiagnosticLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the SignalRServiceDiagnosticLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Client connection IDs  


Summary of the connection IDs which are client connections.  

```query
SignalRServiceDiagnosticLogs
| where ConnectionType == "Client"
| summarize count() by ConnectionId, _ResourceId
```



### Connection close reasons  


Summary of close reasons for disconnected connections.  

```query
SignalRServiceDiagnosticLogs
| where OperationName == "ConnectionAborted" or OperationName == "ConnectionEnded" or OperationName == "EndConnectionFailed"
| summarize count() by  ConnectionId, Message, _ResourceId
```



### IP addresses  


Summary of Ips that connected to the service, which is useful to figure out whether same issue has pattern in  IP address.  

```query
SignalRServiceDiagnosticLogs
| where isnotnull(CallerIpAddress) and isnotempty(CallerIpAddress)
| summarize count() by CallerIpAddress, _ResourceId
```



### Logs relating to specific connection ID  


A list of logs which contains specific connection ID.  

```query
SignalRServiceDiagnosticLogs
// Enter ConnectionId value to filter by specific connection ID.
| where ConnectionId == ""
| sort by TimeGenerated asc
| take 100
```



### Logs relating to specific message tracing ID  


A list of logs which contains the specific message tracing ID.  

```query
SignalRServiceDiagnosticLogs
| where OperationName == "ConnectionAborted" or OperationName == "ConnectionEnded" or OperationName == "EndConnectionFailed"
| summarize count() by  ConnectionId, Message, _ResourceId
```



### Logs relating to specific user ID  


A list of logs which contains the specific user ID.  

```query
SignalRServiceDiagnosticLogs
// Enter UserId value to filter by specific user ID.
| where UserId == ""
| sort by TimeGenerated asc
| take 100
```



### Logs with warning or exceptions  


A list of logs which contains warnings or exceptions (latest logs shown first).   

```query
SignalRServiceDiagnosticLogs
| where Level == "Warning" or Level == "Error"
| sort by TimeGenerated desc, Collection asc
| take 100
```



### Server connection IDs  


Summary of the connection IDs which are server connections.  

```query
SignalRServiceDiagnosticLogs
| where ConnectionType == "Server"
| summarize count() by  ConnectionId, _ResourceId
```



### Time chart of operation names  


Chart of operations in time, for getting the trend of the connectivity and messaging events.  

```query
SignalRServiceDiagnosticLogs
| summarize count() by OperationName, bin(TimeGenerated, 1min)
| render timechart
```



### Transport types  


Summary of transport types for connections. Usually Websockets should be the majority by default.  

```query
SignalRServiceDiagnosticLogs
| where isnotnull(TransportType) and isnotempty(TransportType)
| summarize count() by TransportType, _ResourceId
```



### User IDs  


Summary of the user IDs.  

```query
SignalRServiceDiagnosticLogs
| summarize count() by UserId, _ResourceId
```

