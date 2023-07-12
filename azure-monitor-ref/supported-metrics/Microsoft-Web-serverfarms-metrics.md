---
title: Supported metrics - Microsoft.Web/serverfarms
description: Reference for Microsoft.Web/serverfarms metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Web/serverfarms  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Web/serverfarms resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Data In<p><p>The average incoming bandwidth used across all instances of the plan. |`BytesReceived` |Bytes |Total |Instance |Yes|
|Data Out<p><p>The average outgoing bandwidth used across all instances of the plan. |`BytesSent` |Bytes |Total |Instance |Yes|
|CPU Percentage<p><p>The average CPU used across all instances of the plan. |`CpuPercentage` |Percent |Average |Instance |Yes|
|Disk Queue Length<p><p>The average number of both read and write requests that were queued on storage. A high disk queue length is an indication of an app that might be slowing down because of excessive disk I/O. |`DiskQueueLength` |Count |Average |Instance |Yes|
|Http Queue Length<p><p>The average number of HTTP requests that had to sit on the queue before being fulfilled. A high or increasing HTTP Queue length is a symptom of a plan under heavy load. |`HttpQueueLength` |Count |Average |Instance |Yes|
|Memory Percentage<p><p>The average memory used across all instances of the plan. |`MemoryPercentage` |Percent |Average |Instance |Yes|
|Socket Count for Inbound Requests<p><p>The average number of sockets used for incoming HTTP requests across all the instances of the plan. |`SocketInboundAll` |Count |Average |Instance |Yes|
|Socket Count for Loopback Connections<p><p>The average number of sockets used for loopback connections across all the instances of the plan. |`SocketLoopback` |Count |Average |Instance |Yes|
|Socket Count of Outbound Requests<p><p>The average number of sockets used for outbound connections across all the instances of the plan irrespective of their TCP states. Having too many outbound connections can cause connectivity errors. |`SocketOutboundAll` |Count |Average |Instance |Yes|
|Established Socket Count for Outbound Requests<p><p>The average number of sockets in ESTABLISHED state used for outbound connections across all the instances of the plan. |`SocketOutboundEstablished` |Count |Average |Instance |Yes|
|Time Wait Socket Count for Outbound Requests<p><p>The average number of sockets in TIME_WAIT state used for outbound connections across all the instances of the plan. High or increasing outbound socket counts in TIME_WAIT state can cause connectivity errors. |`SocketOutboundTimeWait` |Count |Average |Instance |Yes|
|TCP Close Wait<p><p>The average number of sockets in CLOSE_WAIT state across all the instances of the plan. |`TcpCloseWait` |Count |Average |Instance |Yes|
|TCP Closing<p><p>The average number of sockets in CLOSING state across all the instances of the plan. |`TcpClosing` |Count |Average |Instance |Yes|
|TCP Established<p><p>The average number of sockets in ESTABLISHED state across all the instances of the plan. |`TcpEstablished` |Count |Average |Instance |Yes|
|TCP Fin Wait 1<p><p>The average number of sockets in FIN_WAIT_1 state across all the instances of the plan. |`TcpFinWait1` |Count |Average |Instance |Yes|
|TCP Fin Wait 2<p><p>The average number of sockets in FIN_WAIT_2 state across all the instances of the plan. |`TcpFinWait2` |Count |Average |Instance |Yes|
|TCP Last Ack<p><p>The average number of sockets in LAST_ACK state across all the instances of the plan. |`TcpLastAck` |Count |Average |Instance |Yes|
|TCP Syn Received<p><p>The average number of sockets in SYN_RCVD state across all the instances of the plan. |`TcpSynReceived` |Count |Average |Instance |Yes|
|TCP Syn Sent<p><p>The average number of sockets in SYN_SENT state across all the instances of the plan. |`TcpSynSent` |Count |Average |Instance |Yes|
|TCP Time Wait<p><p>The average number of sockets in TIME_WAIT state across all the instances of the plan. |`TcpTimeWait` |Count |Average |Instance |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->