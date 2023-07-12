---
title: Supported metrics - Microsoft.ServiceBus/Namespaces
description: Reference for Microsoft.ServiceBus/Namespaces metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ServiceBus/Namespaces  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ServiceBus/Namespaces resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Abandoned Messages<p><p>Count of messages abandoned on a Queue/Topic. |`AbandonMessage` |Count |Total |EntityName |Yes|
|ActiveConnections<p><p>Total Active Connections for Microsoft.ServiceBus. |`ActiveConnections` |Count |Total |No Dimensions |No|
|Count of active messages in a Queue/Topic.<p><p>Count of active messages in a Queue/Topic. |`ActiveMessages` |Count |Average |EntityName |No|
|Completed Messages<p><p>Count of messages completed on a Queue/Topic. |`CompleteMessage` |Count |Total |EntityName |Yes|
|Connections Closed.<p><p>Connections Closed for Microsoft.ServiceBus. |`ConnectionsClosed` |Count |Average |EntityName |No|
|Connections Opened.<p><p>Connections Opened for Microsoft.ServiceBus. |`ConnectionsOpened` |Count |Average |EntityName |No|
|CPU (Deprecated)<p><p>Service bus premium namespace CPU usage metric. This metric is depricated. Please use the CPU metric (NamespaceCpuUsage) instead. |`CPUXNS` |Percent |Maximum |Replica |No|
|Count of dead-lettered messages in a Queue/Topic.<p><p>Count of dead-lettered messages in a Queue/Topic. |`DeadletteredMessages` |Count |Average |EntityName |No|
|Incoming Messages<p><p>Incoming Messages for Microsoft.ServiceBus. |`IncomingMessages` |Count |Total |EntityName |Yes|
|Incoming Requests<p><p>Incoming Requests for Microsoft.ServiceBus. |`IncomingRequests` |Count |Total |EntityName |Yes|
|Count of messages in a Queue/Topic.<p><p>Count of messages in a Queue/Topic. |`Messages` |Count |Average |EntityName |No|
|CPU<p><p>Service bus premium namespace CPU usage metric. |`NamespaceCpuUsage` |Percent |Maximum |Replica |No|
|Memory Usage<p><p>Service bus premium namespace memory usage metric. |`NamespaceMemoryUsage` |Percent |Maximum |Replica |No|
|Outgoing Messages<p><p>Outgoing Messages for Microsoft.ServiceBus. |`OutgoingMessages` |Count |Total |EntityName |Yes|
|Pending Checkpoint Operations Count.<p><p>Pending Checkpoint Operations Count. |`PendingCheckpointOperationCount` |Count |Total |No Dimensions |No|
|Count of scheduled messages in a Queue/Topic.<p><p>Count of scheduled messages in a Queue/Topic. |`ScheduledMessages` |Count |Average |EntityName |No|
|Server Errors.<p><p>Server Errors for Microsoft.ServiceBus. |`ServerErrors` |Count |Total |EntityName, OperationResult |No|
|Server Send Latency.<p><p>Latency of Send Message operations for Service Bus resources. |`ServerSendLatency` |MilliSeconds |Average |EntityName |Yes|
|Size<p><p>Size of an Queue/Topic in Bytes. |`Size` |Bytes |Average |EntityName |No|
|Successful Requests<p><p>Total successful requests for a namespace |`SuccessfulRequests` |Count |Total |EntityName, OperationResult |No|
|Throttled Requests.<p><p>Throttled Requests for Microsoft.ServiceBus. |`ThrottledRequests` |Count |Total |EntityName, OperationResult, MessagingErrorSubCode |No|
|User Errors.<p><p>User Errors for Microsoft.ServiceBus. |`UserErrors` |Count |Total |EntityName, OperationResult |No|
|Memory Usage (Deprecated)<p><p>Service bus premium namespace memory usage metric. This metric is deprecated. Please use the  Memory Usage (NamespaceMemoryUsage) metric instead. |`WSXNS` |Percent |Maximum |Replica |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->