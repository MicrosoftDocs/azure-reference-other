---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/dnszones, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Query Volume<p><p>Number of queries served for a DNS zone |`QueryVolume` |Count |Total |No Dimensions|PT1H |No|
|Record Set Capacity Utilization<p><p>Percent of Record Set capacity utilized by a DNS zone |`RecordSetCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |No Dimensions|PT1H |No|
|Record Set Count<p><p>Number of Record Sets in a DNS zone |`RecordSetCount` |Count |None, Average, Minimum, Maximum, Count |No Dimensions|PT1H |No|