---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/privateDnsZones, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Query Volume**<p><p>Number of queries served for a Private DNS zone |`QueryVolume` |Count |Total |\<none\>| |No|
|**Record Set Capacity Utilization**<p><p>Percent of Record Set capacity utilized by a Private DNS zone |`RecordSetCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |\<none\>| |No|
|**Record Set Count**<p><p>Number of Record Sets in a Private DNS zone |`RecordSetCount` |Count |None, Average, Minimum, Maximum, Count |\<none\>| |No|
|**Virtual Network Link Capacity Utilization**<p><p>Percent of Virtual Network Link capacity utilized by a Private DNS zone |`VirtualNetworkLinkCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |\<none\>| |No|
|**Virtual Network Link Count**<p><p>Number of Virtual Networks linked to a Private DNS zone |`VirtualNetworkLinkCount` |Count |None, Average, Minimum, Maximum, Count |\<none\>| |No|
|**Virtual Network Registration Link Capacity Utilization**<p><p>Percent of Virtual Network Link with auto-registration capacity utilized by a Private DNS zone |`VirtualNetworkWithRegistrationCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |\<none\>| |No|
|**Virtual Network Registration Link Count**<p><p>Number of Virtual Networks linked to a Private DNS zone with auto-registration enabled |`VirtualNetworkWithRegistrationLinkCount` |Count |None, Average, Minimum, Maximum, Count |\<none\>| |No|