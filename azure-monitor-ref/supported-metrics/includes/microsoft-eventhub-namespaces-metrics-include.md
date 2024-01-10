---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventHub/Namespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**ActiveConnections**<p><p>Total Active Connections for Microsoft.EventHub. |`ActiveConnections` |Count |Maximum, Minimum, Average |\<none\>|PT1M |No|
|**Capture Backlog.**<p><p>Capture Backlog for Microsoft.EventHub. |`CaptureBacklog` |Count |Total |`EntityName`|PT1M |No|
|**Captured Bytes.**<p><p>Captured Bytes for Microsoft.EventHub. |`CapturedBytes` |Bytes |Total |`EntityName`|PT1M |No|
|**Captured Messages.**<p><p>Captured Messages for Microsoft.EventHub. |`CapturedMessages` |Count |Total |`EntityName`|PT1M |No|
|**Connections Closed.**<p><p>Connections Closed for Microsoft.EventHub. |`ConnectionsClosed` |Count |Maximum |`EntityName`|PT1M |No|
|**Connections Opened.**<p><p>Connections Opened for Microsoft.EventHub. |`ConnectionsOpened` |Count |Maximum |`EntityName`|PT1M |No|
|**Archive backlog messages (Deprecated)**<p><p>Event Hub archive messages in backlog for a namespace (Deprecated) |`EHABL` |Count |Total |\<none\>|PT1M |Yes|
|**Archive message throughput (Deprecated)**<p><p>Event Hub archived message throughput in a namespace (Deprecated) |`EHAMBS` |Bytes |Total |\<none\>|PT1M |Yes|
|**Archive messages (Deprecated)**<p><p>Event Hub archived messages in a namespace (Deprecated) |`EHAMSGS` |Count |Total |\<none\>|PT1M |Yes|
|**Incoming bytes (Deprecated)**<p><p>Event Hub incoming message throughput for a namespace (Deprecated) |`EHINBYTES` |Bytes |Total |\<none\>|PT1M |Yes|
|**Incoming bytes (obsolete) (Deprecated)**<p><p>Event Hub incoming message throughput for a namespace. This metric is deprecated. Please use Incoming bytes metric instead (Deprecated) |`EHINMBS` |Bytes |Total |\<none\>|PT1M |Yes|
|**Incoming Messages (Deprecated)**<p><p>Total incoming messages for a namespace (Deprecated) |`EHINMSGS` |Count |Total |\<none\>|PT1M |Yes|
|**Outgoing bytes (Deprecated)**<p><p>Event Hub outgoing message throughput for a namespace (Deprecated) |`EHOUTBYTES` |Bytes |Total |\<none\>|PT1M |Yes|
|**Outgoing bytes (obsolete) (Deprecated)**<p><p>Event Hub outgoing message throughput for a namespace. This metric is deprecated. Please use Outgoing bytes metric instead (Deprecated) |`EHOUTMBS` |Bytes |Total |\<none\>|PT1M |Yes|
|**Outgoing Messages (Deprecated)**<p><p>Total outgoing messages for a namespace (Deprecated) |`EHOUTMSGS` |Count |Total |\<none\>|PT1M |Yes|
|**Failed Requests (Deprecated)**<p><p>Total failed requests for a namespace (Deprecated) |`FAILREQ` |Count |Total |\<none\>|PT1M |Yes|
|**Incoming Bytes.**<p><p>Incoming Bytes for Microsoft.EventHub. |`IncomingBytes` |Bytes |Total |`EntityName`|PT1M |Yes|
|**Incoming Messages**<p><p>Incoming Messages for Microsoft.EventHub. |`IncomingMessages` |Count |Total |`EntityName`|PT1M |Yes|
|**Incoming Requests**<p><p>Incoming Requests for Microsoft.EventHub. |`IncomingRequests` |Count |Total |`EntityName`|PT1M |Yes|
|**Incoming Messages (obsolete) (Deprecated)**<p><p>Total incoming messages for a namespace. This metric is deprecated. Please use Incoming Messages metric instead (Deprecated) |`INMSGS` |Count |Total |\<none\>|PT1M |Yes|
|**Incoming Requests (Deprecated)**<p><p>Total incoming send requests for a namespace (Deprecated) |`INREQS` |Count |Total |\<none\>|PT1M |Yes|
|**Internal Server Errors (Deprecated)**<p><p>Total internal server errors for a namespace (Deprecated) |`INTERR` |Count |Total |\<none\>|PT1M |Yes|
|**Other Errors (Deprecated)**<p><p>Total failed requests for a namespace (Deprecated) |`MISCERR` |Count |Total |\<none\>|PT1M |Yes|
|**CPU**<p><p>CPU usage metric for Premium SKU namespaces. |`NamespaceCpuUsage` |Percent |Maximum, Minimum, Average |`Replica`|PT1M |No|
|**Memory Usage**<p><p>Memory usage metric for Premium SKU namespaces. |`NamespaceMemoryUsage` |Percent |Maximum, Minimum, Average |`Replica`|PT1M |No|
|**Outgoing Bytes.**<p><p>Outgoing Bytes for Microsoft.EventHub. |`OutgoingBytes` |Bytes |Total |`EntityName`|PT1M |Yes|
|**Outgoing Messages**<p><p>Outgoing Messages for Microsoft.EventHub. |`OutgoingMessages` |Count |Total |`EntityName`|PT1M |Yes|
|**Outgoing Messages (obsolete) (Deprecated)**<p><p>Total outgoing messages for a namespace. This metric is deprecated. Please use Outgoing Messages metric instead (Deprecated) |`OUTMSGS` |Count |Total |\<none\>|PT1M |Yes|
|**Quota Exceeded Errors.**<p><p>Quota Exceeded Errors for Microsoft.EventHub. |`QuotaExceededErrors` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Server Errors.**<p><p>Server Errors for Microsoft.EventHub. |`ServerErrors` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Size**<p><p>Size of an EventHub in Bytes. |`Size` |Bytes |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**Successful Requests**<p><p>Successful Requests for Microsoft.EventHub. |`SuccessfulRequests` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Successful Requests (Deprecated)**<p><p>Total successful requests for a namespace (Deprecated) |`SUCCREQ` |Count |Total |\<none\>|PT1M |Yes|
|**Server Busy Errors (Deprecated)**<p><p>Total server busy errors for a namespace (Deprecated) |`SVRBSY` |Count |Total |\<none\>|PT1M |Yes|
|**Throttled Requests.**<p><p>Throttled Requests for Microsoft.EventHub. |`ThrottledRequests` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**User Errors.**<p><p>User Errors for Microsoft.EventHub. |`UserErrors` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|