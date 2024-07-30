---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Network/privateDnsZones, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Query Volume**<br><br>Number of queries served for a Private DNS zone |`QueryVolume` |Count |Total |\<none\>| |No|
|**Record Set Capacity Utilization**<br><br>Percent of Record Set capacity utilized by a Private DNS zone |`RecordSetCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |\<none\>| |No|
|**Record Set Count**<br><br>Number of Record Sets in a Private DNS zone |`RecordSetCount` |Count |None, Average, Minimum, Maximum, Count |\<none\>| |No|
|**Virtual Network Link Capacity Utilization**<br><br>Percent of Virtual Network Link capacity utilized by a Private DNS zone |`VirtualNetworkLinkCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |\<none\>| |No|
|**Virtual Network Link Count**<br><br>Number of Virtual Networks linked to a Private DNS zone |`VirtualNetworkLinkCount` |Count |None, Average, Minimum, Maximum, Count |\<none\>| |No|
|**Virtual Network Registration Link Capacity Utilization**<br><br>Percent of Virtual Network Link with auto-registration capacity utilized by a Private DNS zone |`VirtualNetworkWithRegistrationCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |\<none\>| |No|
|**Virtual Network Registration Link Count**<br><br>Number of Virtual Networks linked to a Private DNS zone with auto-registration enabled |`VirtualNetworkWithRegistrationLinkCount` |Count |None, Average, Minimum, Maximum, Count |\<none\>| |No|