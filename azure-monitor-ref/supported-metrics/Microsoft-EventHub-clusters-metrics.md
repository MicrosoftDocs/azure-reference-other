---
title: Supported metrics - Microsoft.EventHub/clusters
description: Reference for Microsoft.EventHub/clusters metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.EventHub/clusters  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.EventHub/clusters resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|ActiveConnections<p><p>Total Active Connections for Microsoft.EventHub. |`ActiveConnections` |Count |Average |No Dimensions |No|
|Available Memory<p><p>Available memory for the Event Hub Cluster as a percentage of total memory. |`AvailableMemory` |Percent |Maximum |Role |No|
|Capture Backlog.<p><p>Capture Backlog for Microsoft.EventHub. |`CaptureBacklog` |Count |Total |No Dimensions |No|
|Captured Bytes.<p><p>Captured Bytes for Microsoft.EventHub. |`CapturedBytes` |Bytes |Total |No Dimensions |No|
|Captured Messages.<p><p>Captured Messages for Microsoft.EventHub. |`CapturedMessages` |Count |Total |No Dimensions |No|
|Connections Closed.<p><p>Connections Closed for Microsoft.EventHub. |`ConnectionsClosed` |Count |Average |No Dimensions |No|
|Connections Opened.<p><p>Connections Opened for Microsoft.EventHub. |`ConnectionsOpened` |Count |Average |No Dimensions |No|
|CPU<p><p>CPU utilization for the Event Hub Cluster as a percentage |`CPU` |Percent |Maximum |Role |No|
|Incoming Bytes.<p><p>Incoming Bytes for Microsoft.EventHub. |`IncomingBytes` |Bytes |Total |No Dimensions |Yes|
|Incoming Messages<p><p>Incoming Messages for Microsoft.EventHub. |`IncomingMessages` |Count |Total |No Dimensions |Yes|
|Incoming Requests<p><p>Incoming Requests for Microsoft.EventHub. |`IncomingRequests` |Count |Total |No Dimensions |Yes|
|Outgoing Bytes.<p><p>Outgoing Bytes for Microsoft.EventHub. |`OutgoingBytes` |Bytes |Total |No Dimensions |Yes|
|Outgoing Messages<p><p>Outgoing Messages for Microsoft.EventHub. |`OutgoingMessages` |Count |Total |No Dimensions |Yes|
|Quota Exceeded Errors.<p><p>Quota Exceeded Errors for Microsoft.EventHub. |`QuotaExceededErrors` |Count |Total |OperationResult |No|
|Server Errors.<p><p>Server Errors for Microsoft.EventHub. |`ServerErrors` |Count |Total |OperationResult |No|
|Size<p><p>Size of an EventHub in Bytes. |`Size` |Bytes |Average |Role |No|
|Successful Requests<p><p>Successful Requests for Microsoft.EventHub. |`SuccessfulRequests` |Count |Total |OperationResult |No|
|Throttled Requests.<p><p>Throttled Requests for Microsoft.EventHub. |`ThrottledRequests` |Count |Total |OperationResult |No|
|User Errors.<p><p>User Errors for Microsoft.EventHub. |`UserErrors` |Count |Total |OperationResult |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->