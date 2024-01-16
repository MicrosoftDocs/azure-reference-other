---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.compute/disks, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Disk Performance|**Disk Read Bytes/sec(Preview)**<p><p>Bytes/sec read from disk during monitoring period, please note, this metric is in preview and is subject to change before becoming generally available |`Composite Disk Read Bytes/sec` |BytesPerSecond |Average |\<none\>|PT1M |No|
|Disk Performance|**Disk Read Operations/sec(Preview)**<p><p>Number of read IOs performed on a disk during monitoring period, please note, this metric is in preview and is subject to change before becoming generally available |`Composite Disk Read Operations/sec` |CountPerSecond |Average |\<none\>|PT1M |No|
|Disk Performance|**Disk Write Bytes/sec(Preview)**<p><p>Bytes/sec written to disk during monitoring period, please note, this metric is in preview and is subject to change before becoming generally available |`Composite Disk Write Bytes/sec` |BytesPerSecond |Average |\<none\>|PT1M |No|
|Disk Performance|**Disk Write Operations/sec(Preview)**<p><p>Number of Write IOs performed on a disk during monitoring period, please note, this metric is in preview and is subject to change before becoming generally available |`Composite Disk Write Operations/sec` |CountPerSecond |Average |\<none\>|PT1M |No|
|Disk Performance|**Disk On-demand Burst Operations(Preview)**<p><p>The accumulated operations of burst transactions used for disks with on-demand burst enabled. Emitted on an hour interval |`DiskPaidBurstIOPS` |Count |Average |\<none\>|PT1M |No|