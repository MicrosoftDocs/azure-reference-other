---
ms.service: azure-monitor
ms.topic: include
ms.date: 05/06/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventHub/Namespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**ActiveConnections**<br><br>Total Active Connections for Microsoft.EventHub. |`ActiveConnections` |Count |Maximum, Minimum, Average |\<none\>|PT1M |No|
|**Capture Backlog.**<br><br>Capture Backlog for Microsoft.EventHub. |`CaptureBacklog` |Count |Total |`EntityName`|PT1M |No|
|**Captured Bytes.**<br><br>Captured Bytes for Microsoft.EventHub. |`CapturedBytes` |Bytes |Total |`EntityName`|PT1M |No|
|**Captured Messages.**<br><br>Captured Messages for Microsoft.EventHub. |`CapturedMessages` |Count |Total |`EntityName`|PT1M |No|
|**Connections Closed.**<br><br>Connections Closed for Microsoft.EventHub. |`ConnectionsClosed` |Count |Maximum |`EntityName`|PT1M |No|
|**Connections Opened.**<br><br>Connections Opened for Microsoft.EventHub. |`ConnectionsOpened` |Count |Maximum |`EntityName`|PT1M |No|
|**Archive backlog messages (Deprecated)**<br><br>Event Hub archive messages in backlog for a namespace (Deprecated) |`EHABL` |Count |Total |\<none\>|PT1M |Yes|
|**Archive message throughput (Deprecated)**<br><br>Event Hub archived message throughput in a namespace (Deprecated) |`EHAMBS` |Bytes |Total |\<none\>|PT1M |Yes|
|**Archive messages (Deprecated)**<br><br>Event Hub archived messages in a namespace (Deprecated) |`EHAMSGS` |Count |Total |\<none\>|PT1M |Yes|
|**Incoming bytes (Deprecated)**<br><br>Event Hub incoming message throughput for a namespace (Deprecated) |`EHINBYTES` |Bytes |Total |\<none\>|PT1M |Yes|
|**Incoming bytes (obsolete) (Deprecated)**<br><br>Event Hub incoming message throughput for a namespace. This metric is deprecated. Please use Incoming bytes metric instead (Deprecated) |`EHINMBS` |Bytes |Total |\<none\>|PT1M |Yes|
|**Incoming Messages (Deprecated)**<br><br>Total incoming messages for a namespace (Deprecated) |`EHINMSGS` |Count |Total |\<none\>|PT1M |Yes|
|**Outgoing bytes (Deprecated)**<br><br>Event Hub outgoing message throughput for a namespace (Deprecated) |`EHOUTBYTES` |Bytes |Total |\<none\>|PT1M |Yes|
|**Outgoing bytes (obsolete) (Deprecated)**<br><br>Event Hub outgoing message throughput for a namespace. This metric is deprecated. Please use Outgoing bytes metric instead (Deprecated) |`EHOUTMBS` |Bytes |Total |\<none\>|PT1M |Yes|
|**Outgoing Messages (Deprecated)**<br><br>Total outgoing messages for a namespace (Deprecated) |`EHOUTMSGS` |Count |Total |\<none\>|PT1M |Yes|
|**Failed Requests (Deprecated)**<br><br>Total failed requests for a namespace (Deprecated) |`FAILREQ` |Count |Total |\<none\>|PT1M |Yes|
|**Incoming Bytes.**<br><br>Incoming Bytes for Microsoft.EventHub. |`IncomingBytes` |Bytes |Total |`EntityName`|PT1M |Yes|
|**Incoming Messages**<br><br>Incoming Messages for Microsoft.EventHub. |`IncomingMessages` |Count |Total |`EntityName`|PT1M |Yes|
|**Incoming Requests**<br><br>Incoming Requests for Microsoft.EventHub. |`IncomingRequests` |Count |Total |`EntityName`|PT1M |Yes|
|**Incoming Messages (obsolete) (Deprecated)**<br><br>Total incoming messages for a namespace. This metric is deprecated. Please use Incoming Messages metric instead (Deprecated) |`INMSGS` |Count |Total |\<none\>|PT1M |Yes|
|**Incoming Requests (Deprecated)**<br><br>Total incoming send requests for a namespace (Deprecated) |`INREQS` |Count |Total |\<none\>|PT1M |Yes|
|**Internal Server Errors (Deprecated)**<br><br>Total internal server errors for a namespace (Deprecated) |`INTERR` |Count |Total |\<none\>|PT1M |Yes|
|**Other Errors (Deprecated)**<br><br>Total failed requests for a namespace (Deprecated) |`MISCERR` |Count |Total |\<none\>|PT1M |Yes|
|**CPU**<br><br>CPU usage metric for Premium SKU namespaces. |`NamespaceCpuUsage` |Percent |Maximum, Minimum, Average |`Replica`|PT1M |No|
|**Memory Usage**<br><br>Memory usage metric for Premium SKU namespaces. |`NamespaceMemoryUsage` |Percent |Maximum, Minimum, Average |`Replica`|PT1M |No|
|**Outgoing Bytes.**<br><br>Outgoing Bytes for Microsoft.EventHub. |`OutgoingBytes` |Bytes |Total |`EntityName`|PT1M |Yes|
|**Outgoing Messages**<br><br>Outgoing Messages for Microsoft.EventHub. |`OutgoingMessages` |Count |Total |`EntityName`|PT1M |Yes|
|**Outgoing Messages (obsolete) (Deprecated)**<br><br>Total outgoing messages for a namespace. This metric is deprecated. Please use Outgoing Messages metric instead (Deprecated) |`OUTMSGS` |Count |Total |\<none\>|PT1M |Yes|
|**Quota Exceeded Errors.**<br><br>Quota Exceeded Errors for Microsoft.EventHub. |`QuotaExceededErrors` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**ReplicationLagCount**<br><br>Replication lag by message count |`ReplicationLagCount` |Count |Maximum, Minimum, Average |`EntityName`|PT1M |No|
|**ReplicationLagDuration**<br><br>Replication lag by time duration |`ReplicationLagDuration` |Seconds |Maximum, Minimum, Average |`EntityName`|PT1M |Yes|
|**Server Errors.**<br><br>Server Errors for Microsoft.EventHub. |`ServerErrors` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Size**<br><br>Size of an EventHub in Bytes. |`Size` |Bytes |Average, Minimum, Maximum |`EntityName`|PT1M |No|
|**Successful Requests**<br><br>Successful Requests for Microsoft.EventHub. |`SuccessfulRequests` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**Successful Requests (Deprecated)**<br><br>Total successful requests for a namespace (Deprecated) |`SUCCREQ` |Count |Total |\<none\>|PT1M |Yes|
|**Server Busy Errors (Deprecated)**<br><br>Total server busy errors for a namespace (Deprecated) |`SVRBSY` |Count |Total |\<none\>|PT1M |Yes|
|**Throttled Requests.**<br><br>Throttled Requests for Microsoft.EventHub. |`ThrottledRequests` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**User Errors.**<br><br>User Errors for Microsoft.EventHub. |`UserErrors` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|