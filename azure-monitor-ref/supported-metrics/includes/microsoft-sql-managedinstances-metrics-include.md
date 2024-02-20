---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Sql/managedInstances, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Average CPU percentage**<br><br>Average CPU percentage |`avg_cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**IO bytes read**<br><br>IO bytes read |`io_bytes_read` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**IO bytes written**<br><br>IO bytes written |`io_bytes_written` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**IO requests count**<br><br>IO requests count |`io_requests` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Storage space reserved**<br><br>Storage space reserved |`reserved_storage_mb` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Storage space used**<br><br>Storage space used |`storage_space_used_mb` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Virtual core count**<br><br>Virtual core count |`virtual_core_count` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|