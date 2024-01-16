---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/networkManagers/ipamPools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Saturation|**Compliant resources count**<p><p>Number of compliant resources associated to the pool. |`CompliantResourcesCount` |Count |Average |\<none\>|PT1M |Yes|
|Saturation|**Compliant resources percentage**<p><p>Ratio of compliant resources to total resources associated to the pool. |`CompliantResourcesPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs allocated count**<p><p>Number of IPs in pool that have been allocated. |`IpsAllocatedCount` |Count |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs allocated percentage**<p><p>Percentage of IPs in pool that have been allocated. |`IpsAllocatedPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs available count**<p><p>Number of IPs in the pool that are available. |`IpsAvailableCount` |Count |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs available percentage**<p><p>Number of IPs in the pool that are available. |`IpsAvailablePercentage` |Percent |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs used count**<p><p>Number of IPs in the pool that have been used. |`IpsUsedCount` |Count |Average |\<none\>|PT1M |Yes|
|Saturation|**IPs used percentage**<p><p>Percentage of IPs in the pool that have been used. |`IpsUsedPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|Saturation|**Noncompliant resources count**<p><p>Number of noncompliant resources associated to the pool. |`NoncompliantResourcesCount` |Count |Average |\<none\>|PT1M |Yes|
|Saturation|**Noncompliant resources percentage**<p><p>Ratio of noncompliant resources to total resources associated to the pool. |`NoncompliantResourcesPercentage` |Percent |Average |\<none\>|PT1M |Yes|