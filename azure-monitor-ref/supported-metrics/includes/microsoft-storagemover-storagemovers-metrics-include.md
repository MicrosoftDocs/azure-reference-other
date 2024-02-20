---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.StorageMover/storageMovers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Job runs|**Job Run Scan Throughput Items**<br><br>Job Run scan throughput in items/sec |`JobRunScanThroughputItems` |CountPerSecond |Average, Maximum, Minimum |`JobRunName`|PT1M |Yes|
|Job runs|**Job Run Transfer Throughput Bytes**<br><br>Job Run transfer throughput in bytes/sec |`JobRunTransferThroughputBytes` |BytesPerSecond |Average, Maximum, Minimum |`JobRunName`|PT1M |Yes|
|Job runs|**Job Run Transfer Throughput Items**<br><br>Job Run transfer throughput in items/sec |`JobRunTransferThroughputItems` |CountPerSecond |Average, Maximum, Minimum |`JobRunName`|PT1M |Yes|