---
ms.service: azure-monitor
ms.topic: include
ms.date: 05/06/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.kubernetes/connectedClusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Availability|**Total number of cpu cores in a connected cluster**<br><br>Total number of cpu cores in a connected cluster |`capacity_cpu_cores` |Count |Total, Average |\<none\>|PT1M |Yes|
|Nodes (PREVIEW)|**CPU Usage Percentage**<br><br>Aggregated average CPU utilization measured in percentage across the cluster |`node_cpu_usage_percentage` |Percent |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Disk Used Percentage**<br><br>Disk space used in percent by device |`node_disk_usage_percentage` |Percent |Maximum, Average |`node`, `nodepool`, `device`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Memory RSS Percentage**<br><br>Container RSS memory used in percent |`node_memory_rss_percentage` |Percent |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Memory Working Set Percentage**<br><br>Container working set memory used in percent |`node_memory_working_set_percentage` |Percent |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|