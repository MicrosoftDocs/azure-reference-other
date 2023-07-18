---
title: Supported metrics - Microsoft.SignalRService/WebPubSub
description: Reference for Microsoft.SignalRService/WebPubSub metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.SignalRService/WebPubSub  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.SignalRService/WebPubSub resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Connection Close Count<p><p>The count of connections closed by various reasons. |`ConnectionCloseCount` |Count |Total |ConnectionCloseCategory |Yes|
|Connection Open Count<p><p>The count of new connections opened. |`ConnectionOpenCount` |Count |Total |No Dimensions |Yes|
|Connection Quota Utilization<p><p>The percentage of connection connected relative to connection quota. |`ConnectionQuotaUtilization` |Percent |Maximum |No Dimensions |Yes|
|Inbound Traffic<p><p>The traffic originating from outside to inside of the service. It is aggregated by adding all the bytes of the traffic. |`InboundTraffic` |Bytes |Total |No Dimensions |Yes|
|Outbound Traffic<p><p>The traffic originating from inside to outside of the service. It is aggregated by adding all the bytes of the traffic. |`OutboundTraffic` |Bytes |Total |No Dimensions |Yes|
|Server Load<p><p>SignalR server load. |`ServerLoad` |Percent |Maximum |No Dimensions |No|
|Connection Count<p><p>The number of user connections established to the service. It is aggregated by adding all the online connections. |`TotalConnectionCount` |Count |Maximum |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->