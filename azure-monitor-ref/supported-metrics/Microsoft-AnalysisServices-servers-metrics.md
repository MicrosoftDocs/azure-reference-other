---
title: Supported metrics - Microsoft.AnalysisServices/servers
description: Reference for Microsoft.AnalysisServices/servers metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.AnalysisServices/servers  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.AnalysisServices/servers resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Memory: Cleaner Current Price<p><p>Current price of memory, $/byte/time, normalized to 1000. |`CleanerCurrentPrice` |Count |Average |ServerResourceType |Yes|
|Memory: Cleaner Memory nonshrinkable<p><p>Amount of memory, in bytes, not subject to purging by the background cleaner. |`CleanerMemoryNonshrinkable` |Bytes |Average |ServerResourceType |Yes|
|Memory: Cleaner Memory shrinkable<p><p>Amount of memory, in bytes, subject to purging by the background cleaner. |`CleanerMemoryShrinkable` |Bytes |Average |ServerResourceType |Yes|
|Threads: Command pool busy threads<p><p>Number of busy threads in the command thread pool. |`CommandPoolBusyThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Command pool idle threads<p><p>Number of idle threads in the command thread pool. |`CommandPoolIdleThreads` |Count |Average |ServerResourceType |Yes|
|Command Pool Job Queue Length<p><p>Number of jobs in the queue of the command thread pool. |`CommandPoolJobQueueLength` |Count |Average |ServerResourceType |Yes|
|Connection: Current connections<p><p>Current number of client connections established. |`CurrentConnections` |Count |Average |ServerResourceType |Yes|
|Current User Sessions<p><p>Current number of user sessions established. |`CurrentUserSessions` |Count |Average |ServerResourceType |Yes|
|Threads: Long parsing busy threads<p><p>Number of busy threads in the long parsing thread pool. |`LongParsingBusyThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Long parsing idle threads<p><p>Number of idle threads in the long parsing thread pool. |`LongParsingIdleThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Long parsing job queue length<p><p>Number of jobs in the queue of the long parsing thread pool. |`LongParsingJobQueueLength` |Count |Average |ServerResourceType |Yes|
|M Engine Memory<p><p>Memory usage by mashup engine processes |`mashup_engine_memory_metric` |Bytes |Average |ServerResourceType |Yes|
|M Engine Private Bytes<p><p>Private bytes usage by mashup engine processes. |`mashup_engine_private_bytes_metric` |Bytes |Average |ServerResourceType |Yes|
|M Engine QPU<p><p>QPU usage by mashup engine processes |`mashup_engine_qpu_metric` |Count |Average |ServerResourceType |Yes|
|M Engine Virtual Bytes<p><p>Virtual bytes usage by mashup engine processes. |`mashup_engine_virtual_bytes_metric` |Bytes |Average |ServerResourceType |Yes|
|Memory<p><p>Memory. Range 0-25 GB for S1, 0-50 GB for S2 and 0-100 GB for S4 |`memory_metric` |Bytes |Average |ServerResourceType |Yes|
|Memory Thrashing<p><p>Average memory thrashing. |`memory_thrashing_metric` |Percent |Average |ServerResourceType |Yes|
|Memory: Memory Limit Hard<p><p>Hard memory limit, from configuration file. |`MemoryLimitHard` |Bytes |Average |ServerResourceType |Yes|
|Memory: Memory Limit High<p><p>High memory limit, from configuration file. |`MemoryLimitHigh` |Bytes |Average |ServerResourceType |Yes|
|Memory: Memory Limit Low<p><p>Low memory limit, from configuration file. |`MemoryLimitLow` |Bytes |Average |ServerResourceType |Yes|
|Memory: Memory Limit VertiPaq<p><p>In-memory limit, from configuration file. |`MemoryLimitVertiPaq` |Bytes |Average |ServerResourceType |Yes|
|Memory: Memory Usage<p><p>Memory usage of the server process as used in calculating cleaner memory price. Equal to counter Process\PrivateBytes plus the size of memory-mapped data, ignoring any memory which was mapped or allocated by the xVelocity in-memory analytics engine (VertiPaq) in excess of the xVelocity engine Memory Limit. |`MemoryUsage` |Bytes |Average |ServerResourceType |Yes|
|Private Bytes<p><p>Private bytes. |`private_bytes_metric` |Bytes |Average |ServerResourceType |Yes|
|Threads: Processing pool busy I/O job threads<p><p>Number of threads running I/O jobs in the processing thread pool. |`ProcessingPoolBusyIOJobThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Processing pool busy non-I/O threads<p><p>Number of threads running non-I/O jobs in the processing thread pool. |`ProcessingPoolBusyNonIOThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Processing pool idle I/O job threads<p><p>Number of idle threads for I/O jobs in the processing thread pool. |`ProcessingPoolIdleIOJobThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Processing pool idle non-I/O threads<p><p>Number of idle threads in the processing thread pool dedicated to non-I/O jobs. |`ProcessingPoolIdleNonIOThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Processing pool I/O job queue length<p><p>Number of I/O jobs in the queue of the processing thread pool. |`ProcessingPoolIOJobQueueLength` |Count |Average |ServerResourceType |Yes|
|Processing Pool Job Queue Length<p><p>Number of non-I/O jobs in the queue of the processing thread pool. |`ProcessingPoolJobQueueLength` |Count |Average |ServerResourceType |Yes|
|QPU<p><p>QPU. Range 0-100 for S1, 0-200 for S2 and 0-400 for S4 |`qpu_metric` |Count |Average |ServerResourceType |Yes|
|Query Pool Busy Threads<p><p>Number of busy threads in the query thread pool. |`QueryPoolBusyThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Query pool idle threads<p><p>Number of idle threads for I/O jobs in the processing thread pool. |`QueryPoolIdleThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Query pool job queue lengt<p><p>Number of jobs in the queue of the query thread pool. |`QueryPoolJobQueueLength` |Count |Average |ServerResourceType |Yes|
|Memory: Quota<p><p>Current memory quota, in bytes. Memory quota is also known as a memory grant or memory reservation. |`Quota` |Bytes |Average |ServerResourceType |Yes|
|Memory: Quota Blocked<p><p>Current number of quota requests that are blocked until other memory quotas are freed. |`QuotaBlocked` |Count |Average |ServerResourceType |Yes|
|Processing: Rows converted per sec<p><p>Rate of rows converted during processing. |`RowsConvertedPerSec` |CountPerSecond |Average |ServerResourceType |Yes|
|Processing: Rows read per sec<p><p>Rate of rows read from all relational databases. |`RowsReadPerSec` |CountPerSecond |Average |ServerResourceType |Yes|
|Processing: Rows written per sec<p><p>Rate of rows written during processing. |`RowsWrittenPerSec` |CountPerSecond |Average |ServerResourceType |Yes|
|Threads: Short parsing busy threads<p><p>Number of busy threads in the short parsing thread pool. |`ShortParsingBusyThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Short parsing idle threads<p><p>Number of idle threads in the short parsing thread pool. |`ShortParsingIdleThreads` |Count |Average |ServerResourceType |Yes|
|Threads: Short parsing job queue length<p><p>Number of jobs in the queue of the short parsing thread pool. |`ShortParsingJobQueueLength` |Count |Average |ServerResourceType |Yes|
|Successful Connections Per Sec<p><p>Rate of successful connection completions. |`SuccessfullConnectionsPerSec` |CountPerSecond |Average |ServerResourceType |Yes|
|Total Connection Failures<p><p>Total failed connection attempts. |`TotalConnectionFailures` |Count |Average |ServerResourceType |Yes|
|Total Connection Requests<p><p>Total connection requests. These are arrivals. |`TotalConnectionRequests` |Count |Average |ServerResourceType |Yes|
|Memory: VertiPaq Nonpaged<p><p>Bytes of memory locked in the working set for use by the in-memory engine. |`VertiPaqNonpaged` |Bytes |Average |ServerResourceType |Yes|
|Memory: VertiPaq Paged<p><p>Bytes of paged memory in use for in-memory data. |`VertiPaqPaged` |Bytes |Average |ServerResourceType |Yes|
|Virtual Bytes<p><p>Virtual bytes. |`virtual_bytes_metric` |Bytes |Average |ServerResourceType |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->