---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.StorageCache/amlFilesystems, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Client Read Ops**<p><p>Number of client read ops performed. |`ClientReadOps` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**Client Read Throughput**<p><p>Client read data transfer rate. |`ClientReadThroughput` |BytesPerSecond |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**Client Write Ops**<p><p>Number of client write ops performed. |`ClientWriteOps` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**Client Write Throughput**<p><p>Client write data transfer rate. |`ClientWriteThroughput` |BytesPerSecond |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**MDT Bytes Available**<p><p>Number of bytes marked as available on the MDT. |`MDTBytesAvailable` |Bytes |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Bytes Total**<p><p>Total number of bytes supported on the MDT. |`MDTBytesTotal` |Bytes |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Bytes Used**<p><p>Number of bytes available for use minus the number of bytes marked as free on the MDT. |`MDTBytesUsed` |Bytes |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Client Latency**<p><p>Client latency for all operations to MDTs. |`MDTClientLatency` |MilliSeconds |Minimum, Maximum, Average |`mdtnum`, `operation`|PT1M |No|
|**Client MDT Ops**<p><p>Number of client MDT metadata ops performed. |`MDTClientOps` |Count |Minimum, Maximum, Average |`mdtnum`, `operation`|PT1M |No|
|**MDT Connected Clients**<p><p>Number of client connections (exports) to the MDT |`MDTConnectedClients` |Count |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Files Free**<p><p>Count of free files (inodes) on the MDT. |`MDTFilesFree` |Count |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Files Total**<p><p>Total number of files supported on the MDT. |`MDTFilesTotal` |Count |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**MDT Files Used**<p><p>Number of total supported files minus the number of free files on the MDT. |`MDTFilesUsed` |Count |Minimum, Maximum, Average |`mdtnum`|PT1M |No|
|**OST Bytes Available**<p><p>Number of bytes marked as available on the OST. |`OSTBytesAvailable` |Bytes |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Bytes Total**<p><p>Total number of bytes supported on the OST. |`OSTBytesTotal` |Bytes |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Bytes Used**<p><p>Number of bytes available for use minus the number of bytes marked as free on the OST. |`OSTBytesUsed` |Bytes |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Client Latency**<p><p>Client latency for all operations to OSTs. |`OSTClientLatency` |MilliSeconds |Minimum, Maximum, Average |`ostnum`, `operation`|PT1M |No|
|**Client OST Ops**<p><p>Number of client OST metadata ops performed. |`OSTClientOps` |Count |Minimum, Maximum, Average |`ostnum`, `operation`|PT1M |No|
|**OST Connected Clients**<p><p>Number of client connections (exports) to the OST |`OSTConnectedClients` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Files Free**<p><p>Count of free files (inodes) on the OST. |`OSTFilesFree` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Files Total**<p><p>Total number of files supported on the OST. |`OSTFilesTotal` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|
|**OST Files Used**<p><p>Number of total supported files minus the number of free files on the OST. |`OSTFilesUsed` |Count |Minimum, Maximum, Average |`ostnum`|PT1M |No|