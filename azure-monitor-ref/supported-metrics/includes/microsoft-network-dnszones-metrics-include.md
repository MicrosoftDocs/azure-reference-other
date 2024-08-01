---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Network/dnszones, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Query Volume**<br><br>Number of queries served for a DNS zone |`QueryVolume` |Count |Total |\<none\>|PT1H |No|
|**Record Set Capacity Utilization**<br><br>Percent of Record Set capacity utilized by a DNS zone |`RecordSetCapacityUtilization` |Percent |None, Average, Minimum, Maximum, Count |\<none\>|PT1H |No|
|**Record Set Count**<br><br>Number of Record Sets in a DNS zone |`RecordSetCount` |Count |None, Average, Minimum, Maximum, Count |\<none\>|PT1H |No|