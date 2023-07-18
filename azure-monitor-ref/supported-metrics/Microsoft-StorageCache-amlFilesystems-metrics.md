---
title: Supported metrics - Microsoft.StorageCache/amlFilesystems
description: Reference for Microsoft.StorageCache/amlFilesystems metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.StorageCache/amlFilesystems  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.StorageCache/amlFilesystems resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Client Read Ops<p><p>Number of client read ops performed. |`ClientReadOps` |Count |Average |ostnum |No|
|Client Read Throughput<p><p>Client read data transfer rate. |`ClientReadThroughput` |BytesPerSecond |Average |ostnum |No|
|Client Write Ops<p><p>Number of client write ops performed. |`ClientWriteOps` |Count |Average |ostnum |No|
|Client Write Throughput<p><p>Client write data transfer rate. |`ClientWriteThroughput` |BytesPerSecond |Average |ostnum |No|
|MDT Bytes Available<p><p>Number of bytes marked as available on the MDT. |`MDTBytesAvailable` |Bytes |Average |mdtnum |No|
|MDT Bytes Total<p><p>Total number of bytes supported on the MDT. |`MDTBytesTotal` |Bytes |Average |mdtnum |No|
|MDT Bytes Used<p><p>Number of bytes available for use minus the number of bytes marked as free on the MDT. |`MDTBytesUsed` |Bytes |Average |mdtnum |No|
|MDT Client Latency<p><p>Client latency for all operations to MDTs. |`MDTClientLatency` |MilliSeconds |Average |mdtnum, operation |No|
|Client MDT Ops<p><p>Number of client MDT metadata ops performed. |`MDTClientOps` |Count |Average |mdtnum, operation |No|
|MDT Connected Clients<p><p>Number of client connections (exports) to the MDT |`MDTConnectedClients` |Count |Average |mdtnum |No|
|MDT Files Free<p><p>Count of free files (inodes) on the MDT. |`MDTFilesFree` |Count |Average |mdtnum |No|
|MDT Files Total<p><p>Total number of files supported on the MDT. |`MDTFilesTotal` |Count |Average |mdtnum |No|
|MDT Files Used<p><p>Number of total supported files minus the number of free files on the MDT. |`MDTFilesUsed` |Count |Average |mdtnum |No|
|OST Bytes Available<p><p>Number of bytes marked as available on the OST. |`OSTBytesAvailable` |Bytes |Average |ostnum |No|
|OST Bytes Total<p><p>Total number of bytes supported on the OST. |`OSTBytesTotal` |Bytes |Average |ostnum |No|
|OST Bytes Used<p><p>Number of bytes available for use minus the number of bytes marked as free on the OST. |`OSTBytesUsed` |Bytes |Average |ostnum |No|
|OST Client Latency<p><p>Client latency for all operations to OSTs. |`OSTClientLatency` |MilliSeconds |Average |ostnum, operation |No|
|Client OST Ops<p><p>Number of client OST metadata ops performed. |`OSTClientOps` |Count |Average |ostnum, operation |No|
|OST Connected Clients<p><p>Number of client connections (exports) to the OST |`OSTConnectedClients` |Count |Average |ostnum |No|
|OST Files Free<p><p>Count of free files (inodes) on the OST. |`OSTFilesFree` |Count |Average |ostnum |No|
|OST Files Total<p><p>Total number of files supported on the OST. |`OSTFilesTotal` |Count |Average |ostnum |No|
|OST Files Used<p><p>Number of total supported files minus the number of free files on the OST. |`OSTFilesUsed` |Count |Average |ostnum |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->