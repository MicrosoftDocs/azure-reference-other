---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/privateDnsZones, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Query Volume<p><p>Number of queries served for a Private DNS zone |`QueryVolume` |Count |Total |No Dimensions| |No|
|Record Set Capacity Utilization<p><p>Percent of Record Set capacity utilized by a Private DNS zone |`RecordSetCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |No Dimensions| |No|
|Record Set Count<p><p>Number of Record Sets in a Private DNS zone |`RecordSetCount` |Count |None, Average, Minimum, Maximum, Count |No Dimensions| |No|
|Virtual Network Link Capacity Utilization<p><p>Percent of Virtual Network Link capacity utilized by a Private DNS zone |`VirtualNetworkLinkCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |No Dimensions| |No|
|Virtual Network Link Count<p><p>Number of Virtual Networks linked to a Private DNS zone |`VirtualNetworkLinkCount` |Count |None, Average, Minimum, Maximum, Count |No Dimensions| |No|
|Virtual Network Registration Link Capacity Utilization<p><p>Percent of Virtual Network Link with auto-registration capacity utilized by a Private DNS zone |`VirtualNetworkWithRegistrationCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |No Dimensions| |No|
|Virtual Network Registration Link Count<p><p>Number of Virtual Networks linked to a Private DNS zone with auto-registration enabled |`VirtualNetworkWithRegistrationLinkCount` |Count |None, Average, Minimum, Maximum, Count |No Dimensions| |No|