---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ClusterStor/nodes, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|TotalCapacityAvailable<p><p>The total capacity available in lustre file system |`TotalCapacityAvailable` |Bytes |Average |filesystem_name, category, system|PT1M |No|
|TotalCapacityUsed<p><p>The total capacity used in lustre file system |`TotalCapacityUsed` |Bytes |Average |filesystem_name, category, system|PT1M |No|
|TotalRead<p><p>The total lustre file system read per second |`TotalRead` |BytesPerSecond |Average |filesystem_name, category, system|PT1M |No|
|TotalWrite<p><p>The total lustre file system write per second |`TotalWrite` |BytesPerSecond |Average |filesystem_name, category, system|PT1M |No|