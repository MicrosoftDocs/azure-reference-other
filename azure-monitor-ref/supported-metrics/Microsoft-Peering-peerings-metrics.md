---
title: Supported metrics - Microsoft.Peering/peerings
description: Reference for Microsoft.Peering/peerings metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Peering/peerings  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Peering/peerings resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Average Customer Prefix Latency<p><p>Average of median Customer prefix latency |`AverageCustomerPrefixLatency` |Milliseconds |Average |RegisteredAsnName |Yes|
|Egress Traffic Rate<p><p>Egress traffic rate in bits per second |`EgressTrafficRate` |BitsPerSecond |Average |ConnectionId, SessionIp, TrafficClass |Yes|
|Connection Flap Events Count<p><p>Flap Events Count in all the connection |`FlapCounts` |Count |Sum |ConnectionId, SessionIp |Yes|
|Ingress Traffic Rate<p><p>Ingress traffic rate in bits per second |`IngressTrafficRate` |BitsPerSecond |Average |ConnectionId, SessionIp, TrafficClass |Yes|
|Packets Drop Rate<p><p>Packets Drop rate in bits per second |`PacketDropRate` |BitsPerSecond |Average |ConnectionId, SessionIp, TrafficClass |Yes|
|Prefix Latency<p><p>Median prefix latency |`RegisteredPrefixLatency` |Milliseconds |Average |RegisteredPrefixName |Yes|
|Session Availability<p><p>Availability of the peering session |`SessionAvailability` |Count |Average |ConnectionId, SessionIp |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->