---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/dnszones, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Query Volume**<p><p>Number of queries served for a DNS zone |`QueryVolume` |Count |Total |\<none\>|PT1H |No|
|**Record Set Capacity Utilization**<p><p>Percent of Record Set capacity utilized by a DNS zone |`RecordSetCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |\<none\>|PT1H |No|
|**Record Set Count**<p><p>Number of Record Sets in a DNS zone |`RecordSetCount` |Count |None, Average, Minimum, Maximum, Count |\<none\>|PT1H |No|