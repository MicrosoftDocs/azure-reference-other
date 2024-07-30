---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.ServiceBus/Namespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Abandoned Messages**<br><br>Count of messages abandoned on a Queue/Topic. |`AbandonMessage` |Count |Total |`EntityName`|PT1M |Yes|
|**ActiveConnections**<br><br>Total Active Connections for Microsoft.ServiceBus. |`ActiveConnections` |Count |Total |\<none\>|PT1M |No|
|**Count of active messages in a Queue/Topic.**<br><br>Count of active messages in a Queue/Topic. |`ActiveMessages` |Count |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**Completed Messages**<br><br>Count of messages completed on a Queue/Topic. |`CompleteMessage` |Count |Total |`EntityName`|PT1M |Yes|
|**Connections Closed.**<br><br>Connections Closed for Microsoft.ServiceBus. |`ConnectionsClosed` |Count |Average |`EntityName`|PT1M |No|
|**Connections Opened.**<br><br>Connections Opened for Microsoft.ServiceBus. |`ConnectionsOpened` |Count |Average |`EntityName`|PT1M |No|
|**CPU (Deprecated)**<br><br>Service bus premium namespace CPU usage metric. This metric is depricated. Please use the CPU metric (NamespaceCpuUsage) instead. |`CPUXNS` |Percent |Maximum |`Replica`|PT1M |No|
|**Count of dead-lettered messages in a Queue/Topic.**<br><br>Count of dead-lettered messages in a Queue/Topic. |`DeadletteredMessages` |Count |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**Incoming Messages**<br><br>Incoming Messages for Microsoft.ServiceBus. |`IncomingMessages` |Count |Total |`EntityName`|PT1M |Yes|
|**Incoming Requests**<br><br>Incoming Requests for Microsoft.ServiceBus. |`IncomingRequests` |Count |Total |`EntityName`|PT1M |Yes|
|**Count of messages in a Queue/Topic.**<br><br>Count of messages in a Queue/Topic. |`Messages` |Count |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**CPU**<br><br>Service bus premium namespace CPU usage metric. |`NamespaceCpuUsage` |Percent |Maximum |`Replica`|PT1M |No|
|**Memory Usage**<br><br>Service bus premium namespace memory usage metric. |`NamespaceMemoryUsage` |Percent |Maximum |`Replica`|PT1M |No|
|**Outgoing Messages**<br><br>Outgoing Messages for Microsoft.ServiceBus. |`OutgoingMessages` |Count |Total |`EntityName`|PT1M |Yes|
|**Pending Checkpoint Operations Count.**<br><br>Pending Checkpoint Operations Count. |`PendingCheckpointOperationCount` |Count |Total |\<none\>|PT1M |No|
|**ReplicationLagCount**<br><br>Replication lag by message count |`ReplicationLagCount` |Count |Maximum, Minimum, Average |`EntityName`|PT1M |No|
|**ReplicationLagDuration**<br><br>Replication lag by time duration |`ReplicationLagDuration` |Seconds |Maximum, Minimum, Average |`EntityName`|PT1M |Yes|
|**Count of scheduled messages in a Queue/Topic.**<br><br>Count of scheduled messages in a Queue/Topic. |`ScheduledMessages` |Count |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**Server Errors.**<br><br>Server Errors for Microsoft.ServiceBus. |`ServerErrors` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Server Send Latency.**<br><br>Latency of Send Message operations for Service Bus resources. |`ServerSendLatency` |MilliSeconds |Average |`EntityName`|PT1M |Yes|
|**Size**<br><br>Size of an Queue/Topic in Bytes. |`Size` |Bytes |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**Successful Requests**<br><br>Total successful requests for a namespace |`SuccessfulRequests` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Throttled Requests.**<br><br>Throttled Requests for Microsoft.ServiceBus. |`ThrottledRequests` |Count |Total |`EntityName`, `OperationResult`, `MessagingErrorSubCode`|PT1M |No|
|**User Errors.**<br><br>User Errors for Microsoft.ServiceBus. |`UserErrors` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Memory Usage (Deprecated)**<br><br>Service bus premium namespace memory usage metric. This metric is deprecated. Please use the  Memory Usage (NamespaceMemoryUsage) metric instead. |`WSXNS` |Percent |Maximum |`Replica`|PT1M |No|