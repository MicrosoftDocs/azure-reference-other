---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/networkManagers/ipamPools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Saturation|**Compliant resources count**<br><br>Number of compliant resources associated to the pool. |`CompliantResourcesCount` |Count |Average |\<none\>|PT1M |Yes|
|Saturation|**Compliant resources percentage**<br><br>Ratio of compliant resources to total resources associated to the pool. |`CompliantResourcesPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs allocated count**<br><br>Number of IPs in pool that have been allocated. |`IpsAllocatedCount` |Count |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs allocated percentage**<br><br>Percentage of IPs in pool that have been allocated. |`IpsAllocatedPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs available count**<br><br>Number of IPs in the pool that are available. |`IpsAvailableCount` |Count |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs available percentage**<br><br>Number of IPs in the pool that are available. |`IpsAvailablePercentage` |Percent |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs used count**<br><br>Number of IPs in the pool that have been used. |`IpsUsedCount` |Count |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs used percentage**<br><br>Percentage of IPs in the pool that have been used. |`IpsUsedPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|Saturation|**Noncompliant resources count**<br><br>Number of noncompliant resources associated to the pool. |`NoncompliantResourcesCount` |Count |Average |\<none\>|PT1M |Yes|
|Saturation|**Noncompliant resources percentage**<br><br>Ratio of noncompliant resources to total resources associated to the pool. |`NoncompliantResourcesPercentage` |Percent |Average |\<none\>|PT1M |Yes|