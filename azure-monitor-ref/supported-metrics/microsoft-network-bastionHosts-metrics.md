---
title: Supported metrics - microsoft.network/bastionHosts
description: Reference for microsoft.network/bastionHosts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.network/bastionHosts  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.network/bastionHosts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Bastion Communication Status<p><p>Communication status shows 1 if all communication is good and 0 if its bad. |`pingmesh` |Count |Average |No Dimensions |No|
|Session Count<p><p>Sessions Count for the Bastion. View in sum and per instance. |`sessions` |Count |Total |host |No|
|Total Memory<p><p>Total memory stats. |`total` |Count |Average |host |Yes|
|CPU Usage<p><p>CPU Usage stats. |`usage_user` |Count |Average |cpu, host |No|
|Memory Usage<p><p>Memory Usage stats. |`used` |Count |Average |host |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->