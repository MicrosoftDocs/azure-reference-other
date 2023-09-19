---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Sql/managedInstances, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Average CPU percentage<p><p>Average CPU percentage |`avg_cpu_percent` |Percent |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|IO bytes read<p><p>IO bytes read |`io_bytes_read` |Bytes |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|IO bytes written<p><p>IO bytes written |`io_bytes_written` |Bytes |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|IO requests count<p><p>IO requests count |`io_requests` |Count |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Storage space reserved<p><p>Storage space reserved |`reserved_storage_mb` |Count |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Storage space used<p><p>Storage space used |`storage_space_used_mb` |Count |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Virtual core count<p><p>Virtual core count |`virtual_core_count` |Count |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|