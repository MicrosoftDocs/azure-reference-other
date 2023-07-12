---
title: Supported metrics - Microsoft.Network/dnszones
description: Reference for Microsoft.Network/dnszones metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/dnszones  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Network/dnszones resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Query Volume<p><p>Number of queries served for a DNS zone |`QueryVolume` |Count |Total |No Dimensions |No|
|Record Set Capacity Utilization<p><p>Percent of Record Set capacity utilized by a DNS zone |`RecordSetCapacityUtilization` |Percent |Maximum |No Dimensions |No|
|Record Set Count<p><p>Number of Record Sets in a DNS zone |`RecordSetCount` |Count |Maximum |No Dimensions |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->