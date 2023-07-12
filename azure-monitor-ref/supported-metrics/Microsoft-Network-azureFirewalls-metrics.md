---
title: Supported metrics - Microsoft.Network/azureFirewalls
description: Reference for Microsoft.Network/azureFirewalls metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/azureFirewalls  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Network/azureFirewalls resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Application rules hit count<p><p>Number of times Application rules were hit |`ApplicationRuleHit` |Count |Total |Status, Reason, Protocol |Yes|
|Data processed<p><p>Total amount of data processed by this firewall |`DataProcessed` |Bytes |Total |No Dimensions |Yes|
|Firewall health state<p><p>Indicates the overall health of this firewall |`FirewallHealth` |Percent |Average |Status, Reason |Yes|
|Latency Probe (Preview)<p><p>Estimate of the average latency of the Firewall as measured by latency probe |`FirewallLatencyPng` |Milliseconds |Average |No Dimensions |Yes|
|Network rules hit count<p><p>Number of times Network rules were hit |`NetworkRuleHit` |Count |Total |Status, Reason, Protocol |Yes|
|SNAT port utilization<p><p>Percentage of outbound SNAT ports currently in use |`SNATPortUtilization` |Percent |Average |Protocol |Yes|
|Throughput<p><p>Throughput processed by this firewall |`Throughput` |BitsPerSecond |Average |No Dimensions |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->