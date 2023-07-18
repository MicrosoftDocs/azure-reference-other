---
title: Supported metrics - Microsoft.EventHub/Namespaces
description: Reference for Microsoft.EventHub/Namespaces metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.EventHub/Namespaces  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.EventHub/Namespaces resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|ActiveConnections<p><p>Total Active Connections for Microsoft.EventHub. |`ActiveConnections` |Count |Maximum |No Dimensions |No|
|Capture Backlog.<p><p>Capture Backlog for Microsoft.EventHub. |`CaptureBacklog` |Count |Total |EntityName |No|
|Captured Bytes.<p><p>Captured Bytes for Microsoft.EventHub. |`CapturedBytes` |Bytes |Total |EntityName |No|
|Captured Messages.<p><p>Captured Messages for Microsoft.EventHub. |`CapturedMessages` |Count |Total |EntityName |No|
|Connections Closed.<p><p>Connections Closed for Microsoft.EventHub. |`ConnectionsClosed` |Count |Maximum |EntityName |No|
|Connections Opened.<p><p>Connections Opened for Microsoft.EventHub. |`ConnectionsOpened` |Count |Maximum |EntityName |No|
|Archive backlog messages (Deprecated)<p><p>Event Hub archive messages in backlog for a namespace (Deprecated) |`EHABL` |Count |Total |No Dimensions |Yes|
|Archive message throughput (Deprecated)<p><p>Event Hub archived message throughput in a namespace (Deprecated) |`EHAMBS` |Bytes |Total |No Dimensions |Yes|
|Archive messages (Deprecated)<p><p>Event Hub archived messages in a namespace (Deprecated) |`EHAMSGS` |Count |Total |No Dimensions |Yes|
|Incoming bytes (Deprecated)<p><p>Event Hub incoming message throughput for a namespace (Deprecated) |`EHINBYTES` |Bytes |Total |No Dimensions |Yes|
|Incoming bytes (obsolete) (Deprecated)<p><p>Event Hub incoming message throughput for a namespace. This metric is deprecated. Please use Incoming bytes metric instead (Deprecated) |`EHINMBS` |Bytes |Total |No Dimensions |Yes|
|Incoming Messages (Deprecated)<p><p>Total incoming messages for a namespace (Deprecated) |`EHINMSGS` |Count |Total |No Dimensions |Yes|
|Outgoing bytes (Deprecated)<p><p>Event Hub outgoing message throughput for a namespace (Deprecated) |`EHOUTBYTES` |Bytes |Total |No Dimensions |Yes|
|Outgoing bytes (obsolete) (Deprecated)<p><p>Event Hub outgoing message throughput for a namespace. This metric is deprecated. Please use Outgoing bytes metric instead (Deprecated) |`EHOUTMBS` |Bytes |Total |No Dimensions |Yes|
|Outgoing Messages (Deprecated)<p><p>Total outgoing messages for a namespace (Deprecated) |`EHOUTMSGS` |Count |Total |No Dimensions |Yes|
|Failed Requests (Deprecated)<p><p>Total failed requests for a namespace (Deprecated) |`FAILREQ` |Count |Total |No Dimensions |Yes|
|Incoming Bytes.<p><p>Incoming Bytes for Microsoft.EventHub. |`IncomingBytes` |Bytes |Total |EntityName |Yes|
|Incoming Messages<p><p>Incoming Messages for Microsoft.EventHub. |`IncomingMessages` |Count |Total |EntityName |Yes|
|Incoming Requests<p><p>Incoming Requests for Microsoft.EventHub. |`IncomingRequests` |Count |Total |EntityName |Yes|
|Incoming Messages (obsolete) (Deprecated)<p><p>Total incoming messages for a namespace. This metric is deprecated. Please use Incoming Messages metric instead (Deprecated) |`INMSGS` |Count |Total |No Dimensions |Yes|
|Incoming Requests (Deprecated)<p><p>Total incoming send requests for a namespace (Deprecated) |`INREQS` |Count |Total |No Dimensions |Yes|
|Internal Server Errors (Deprecated)<p><p>Total internal server errors for a namespace (Deprecated) |`INTERR` |Count |Total |No Dimensions |Yes|
|Other Errors (Deprecated)<p><p>Total failed requests for a namespace (Deprecated) |`MISCERR` |Count |Total |No Dimensions |Yes|
|CPU<p><p>CPU usage metric for Premium SKU namespaces. |`NamespaceCpuUsage` |Percent |Maximum |Replica |No|
|Memory Usage<p><p>Memory usage metric for Premium SKU namespaces. |`NamespaceMemoryUsage` |Percent |Maximum |Replica |No|
|Outgoing Bytes.<p><p>Outgoing Bytes for Microsoft.EventHub. |`OutgoingBytes` |Bytes |Total |EntityName |Yes|
|Outgoing Messages<p><p>Outgoing Messages for Microsoft.EventHub. |`OutgoingMessages` |Count |Total |EntityName |Yes|
|Outgoing Messages (obsolete) (Deprecated)<p><p>Total outgoing messages for a namespace. This metric is deprecated. Please use Outgoing Messages metric instead (Deprecated) |`OUTMSGS` |Count |Total |No Dimensions |Yes|
|Quota Exceeded Errors.<p><p>Quota Exceeded Errors for Microsoft.EventHub. |`QuotaExceededErrors` |Count |Total |EntityName, OperationResult |No|
|Server Errors.<p><p>Server Errors for Microsoft.EventHub. |`ServerErrors` |Count |Total |EntityName, OperationResult |No|
|Size<p><p>Size of an EventHub in Bytes. |`Size` |Bytes |Average |EntityName |No|
|Successful Requests<p><p>Successful Requests for Microsoft.EventHub. |`SuccessfulRequests` |Count |Total |EntityName, OperationResult |No|
|Successful Requests (Deprecated)<p><p>Total successful requests for a namespace (Deprecated) |`SUCCREQ` |Count |Total |No Dimensions |Yes|
|Server Busy Errors (Deprecated)<p><p>Total server busy errors for a namespace (Deprecated) |`SVRBSY` |Count |Total |No Dimensions |Yes|
|Throttled Requests.<p><p>Throttled Requests for Microsoft.EventHub. |`ThrottledRequests` |Count |Total |EntityName, OperationResult |No|
|User Errors.<p><p>User Errors for Microsoft.EventHub. |`UserErrors` |Count |Total |EntityName, OperationResult |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->