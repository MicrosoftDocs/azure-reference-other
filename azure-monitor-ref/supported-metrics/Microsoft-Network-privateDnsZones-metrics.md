---
title: Supported metrics - Microsoft.Network/privateDnsZones
description: Reference for Microsoft.Network/privateDnsZones metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/privateDnsZones  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Network/privateDnsZones resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Query Volume<p><p>Number of queries served for a Private DNS zone |`QueryVolume` |Count |Total |No Dimensions |No|
|Record Set Capacity Utilization<p><p>Percent of Record Set capacity utilized by a Private DNS zone |`RecordSetCapacityUtilization` |Percent |Maximum |No Dimensions |No|
|Record Set Count<p><p>Number of Record Sets in a Private DNS zone |`RecordSetCount` |Count |Maximum |No Dimensions |No|
|Virtual Network Link Capacity Utilization<p><p>Percent of Virtual Network Link capacity utilized by a Private DNS zone |`VirtualNetworkLinkCapacityUtilization` |Percent |Maximum |No Dimensions |No|
|Virtual Network Link Count<p><p>Number of Virtual Networks linked to a Private DNS zone |`VirtualNetworkLinkCount` |Count |Maximum |No Dimensions |No|
|Virtual Network Registration Link Capacity Utilization<p><p>Percent of Virtual Network Link with auto-registration capacity utilized by a Private DNS zone |`VirtualNetworkWithRegistrationCapacityUtilization` |Percent |Maximum |No Dimensions |No|
|Virtual Network Registration Link Count<p><p>Number of Virtual Networks linked to a Private DNS zone with auto-registration enabled |`VirtualNetworkWithRegistrationLinkCount` |Count |Maximum |No Dimensions |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->