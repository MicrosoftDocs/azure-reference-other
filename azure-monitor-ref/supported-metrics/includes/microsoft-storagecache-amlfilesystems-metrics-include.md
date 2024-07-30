---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.StorageCache/amlFilesystems, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Client Read Ops**<br><br>Number of client read ops performed. |`ClientReadOps` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**Client Read Throughput**<br><br>Client read data transfer rate. |`ClientReadThroughput` |BytesPerSecond |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**Client Write Ops**<br><br>Number of client write ops performed. |`ClientWriteOps` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**Client Write Throughput**<br><br>Client write data transfer rate. |`ClientWriteThroughput` |BytesPerSecond |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**MDT Bytes Available**<br><br>Number of bytes marked as available on the MDT. |`MDTBytesAvailable` |Bytes |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Bytes Total**<br><br>Total number of bytes supported on the MDT. |`MDTBytesTotal` |Bytes |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Bytes Used**<br><br>Number of bytes available for use minus the number of bytes marked as free on the MDT. |`MDTBytesUsed` |Bytes |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Client Latency**<br><br>Client latency for all operations to MDTs. |`MDTClientLatency` |MilliSeconds |Minimum, Maximum, Average |`mdtnum`, `operation`|PT1M |No|
|**Client MDT Ops**<br><br>Number of client MDT metadata ops performed. |`MDTClientOps` |Count |Minimum, Maximum, Average |`mdtnum`, `operation`|PT1M |No|
|**MDT Connected Clients**<br><br>Number of client connections (exports) to the MDT |`MDTConnectedClients` |Count |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Files Free**<br><br>Count of free files (inodes) on the MDT. |`MDTFilesFree` |Count |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Files Total**<br><br>Total number of files supported on the MDT. |`MDTFilesTotal` |Count |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Files Used**<br><br>Number of total supported files minus the number of free files on the MDT. |`MDTFilesUsed` |Count |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**OST Bytes Available**<br><br>Number of bytes marked as available on the OST. |`OSTBytesAvailable` |Bytes |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Bytes Total**<br><br>Total number of bytes supported on the OST. |`OSTBytesTotal` |Bytes |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Bytes Used**<br><br>Number of bytes available for use minus the number of bytes marked as free on the OST. |`OSTBytesUsed` |Bytes |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Client Latency**<br><br>Client latency for all operations to OSTs. |`OSTClientLatency` |MilliSeconds |Minimum, Maximum, Average |`ostnum`, `operation`|PT1M |No|
|**Client OST Ops**<br><br>Number of client OST metadata ops performed. |`OSTClientOps` |Count |Minimum, Maximum, Average |`ostnum`, `operation`|PT1M |No|
|**OST Connected Clients**<br><br>Number of client connections (exports) to the OST |`OSTConnectedClients` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Files Free**<br><br>Count of free files (inodes) on the OST. |`OSTFilesFree` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Files Total**<br><br>Total number of files supported on the OST. |`OSTFilesTotal` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Files Used**<br><br>Number of total supported files minus the number of free files on the OST. |`OSTFilesUsed` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|