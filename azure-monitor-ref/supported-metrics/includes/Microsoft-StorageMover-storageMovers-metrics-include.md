---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.StorageMover/storageMovers, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Job Run Scan Throughput Items<p><p>Job Run scan throughput in items/sec |`JobRunScanThroughputItems` |CountPerSecond |Average, Maximum, Minimum |JobRunName|PT1M |Yes|
|Job Run Transfer Throughput Bytes<p><p>Job Run transfer throughput in bytes/sec |`JobRunTransferThroughputBytes` |BytesPerSecond |Average, Maximum, Minimum |JobRunName|PT1M |Yes|
|Job Run Transfer Throughput Items<p><p>Job Run transfer throughput in items/sec |`JobRunTransferThroughputItems` |CountPerSecond |Average, Maximum, Minimum |JobRunName|PT1M |Yes|