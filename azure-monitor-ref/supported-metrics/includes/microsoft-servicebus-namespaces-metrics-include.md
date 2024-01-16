---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ServiceBus/Namespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Abandoned Messages**<p><p>Count of messages abandoned on a Queue/Topic. |`AbandonMessage` |Count |Total |`EntityName`|PT1M |Yes|
|**ActiveConnections**<p><p>Total Active Connections for Microsoft.ServiceBus. |`ActiveConnections` |Count |Total |\<none\>|PT1M |No|
|**Count of active messages in a Queue/Topic.**<p><p>Count of active messages in a Queue/Topic. |`ActiveMessages` |Count |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**Completed Messages**<p><p>Count of messages completed on a Queue/Topic. |`CompleteMessage` |Count |Total |`EntityName`|PT1M |Yes|
|**Connections Closed.**<p><p>Connections Closed for Microsoft.ServiceBus. |`ConnectionsClosed` |Count |Average |`EntityName`|PT1M |No|
|**Connections Opened.**<p><p>Connections Opened for Microsoft.ServiceBus. |`ConnectionsOpened` |Count |Average |`EntityName`|PT1M |No|
|**CPU (Deprecated)**<p><p>Service bus premium namespace CPU usage metric. This metric is depricated. Please use the CPU metric (NamespaceCpuUsage) instead. |`CPUXNS` |Percent |Maximum |`Replica`|PT1M |No|
|**Count of dead-lettered messages in a Queue/Topic.**<p><p>Count of dead-lettered messages in a Queue/Topic. |`DeadletteredMessages` |Count |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**Incoming Messages**<p><p>Incoming Messages for Microsoft.ServiceBus. |`IncomingMessages` |Count |Total |`EntityName`|PT1M |Yes|
|**Incoming Requests**<p><p>Incoming Requests for Microsoft.ServiceBus. |`IncomingRequests` |Count |Total |`EntityName`|PT1M |Yes|
|**Count of messages in a Queue/Topic.**<p><p>Count of messages in a Queue/Topic. |`Messages` |Count |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**CPU**<p><p>Service bus premium namespace CPU usage metric. |`NamespaceCpuUsage` |Percent |Maximum |`Replica`|PT1M |No|
|**Memory Usage**<p><p>Service bus premium namespace memory usage metric. |`NamespaceMemoryUsage` |Percent |Maximum |`Replica`|PT1M |No|
|**Outgoing Messages**<p><p>Outgoing Messages for Microsoft.ServiceBus. |`OutgoingMessages` |Count |Total |`EntityName`|PT1M |Yes|
|**Pending Checkpoint Operations Count.**<p><p>Pending Checkpoint Operations Count. |`PendingCheckpointOperationCount` |Count |Total |\<none\>|PT1M |No|
|**Count of scheduled messages in a Queue/Topic.**<p><p>Count of scheduled messages in a Queue/Topic. |`ScheduledMessages` |Count |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**Server Errors.**<p><p>Server Errors for Microsoft.ServiceBus. |`ServerErrors` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Server Send Latency.**<p><p>Latency of Send Message operations for Service Bus resources. |`ServerSendLatency` |MilliSeconds |Average |`EntityName`|PT1M |Yes|
|**Size**<p><p>Size of an Queue/Topic in Bytes. |`Size` |Bytes |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**Successful Requests**<p><p>Total successful requests for a namespace |`SuccessfulRequests` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Throttled Requests.**<p><p>Throttled Requests for Microsoft.ServiceBus. |`ThrottledRequests` |Count |Total |`EntityName`, `OperationResult`, `MessagingErrorSubCode`|PT1M |No|
|**User Errors.**<p><p>User Errors for Microsoft.ServiceBus. |`UserErrors` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Memory Usage (Deprecated)**<p><p>Service bus premium namespace memory usage metric. This metric is deprecated. Please use the  Memory Usage (NamespaceMemoryUsage) metric instead. |`WSXNS` |Percent |Maximum |`Replica`|PT1M |No|