---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.AnalysisServices/servers, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Memory: Cleaner Current Price**<p><p>Current price of memory, $/byte/time, normalized to 1000. |`CleanerCurrentPrice` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Cleaner Memory nonshrinkable**<p><p>Amount of memory, in bytes, not subject to purging by the background cleaner. |`CleanerMemoryNonshrinkable` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Cleaner Memory shrinkable**<p><p>Amount of memory, in bytes, subject to purging by the background cleaner. |`CleanerMemoryShrinkable` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Command pool busy threads**<p><p>Number of busy threads in the command thread pool. |`CommandPoolBusyThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Command pool idle threads**<p><p>Number of idle threads in the command thread pool. |`CommandPoolIdleThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Command Pool Job Queue Length**<p><p>Number of jobs in the queue of the command thread pool. |`CommandPoolJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Connection: Current connections**<p><p>Current number of client connections established. |`CurrentConnections` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Current User Sessions**<p><p>Current number of user sessions established. |`CurrentUserSessions` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Long parsing busy threads**<p><p>Number of busy threads in the long parsing thread pool. |`LongParsingBusyThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Long parsing idle threads**<p><p>Number of idle threads in the long parsing thread pool. |`LongParsingIdleThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Long parsing job queue length**<p><p>Number of jobs in the queue of the long parsing thread pool. |`LongParsingJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**M Engine Memory**<p><p>Memory usage by mashup engine processes |`mashup_engine_memory_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**M Engine Private Bytes**<p><p>Private bytes usage by mashup engine processes. |`mashup_engine_private_bytes_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**M Engine QPU**<p><p>QPU usage by mashup engine processes |`mashup_engine_qpu_metric` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**M Engine Virtual Bytes**<p><p>Virtual bytes usage by mashup engine processes. |`mashup_engine_virtual_bytes_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory**<p><p>Memory. Range 0-25 GB for S1, 0-50 GB for S2 and 0-100 GB for S4 |`memory_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory Thrashing**<p><p>Average memory thrashing. |`memory_thrashing_metric` |Percent |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Memory Limit Hard**<p><p>Hard memory limit, from configuration file. |`MemoryLimitHard` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Memory Limit High**<p><p>High memory limit, from configuration file. |`MemoryLimitHigh` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Memory Limit Low**<p><p>Low memory limit, from configuration file. |`MemoryLimitLow` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Memory Limit VertiPaq**<p><p>In-memory limit, from configuration file. |`MemoryLimitVertiPaq` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Memory Usage**<p><p>Memory usage of the server process as used in calculating cleaner memory price. Equal to counter Process\PrivateBytes plus the size of memory-mapped data, ignoring any memory which was mapped or allocated by the xVelocity in-memory analytics engine (VertiPaq) in excess of the xVelocity engine Memory Limit. |`MemoryUsage` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Private Bytes**<p><p>Private bytes. |`private_bytes_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Processing pool busy I/O job threads**<p><p>Number of threads running I/O jobs in the processing thread pool. |`ProcessingPoolBusyIOJobThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Processing pool busy non-I/O threads**<p><p>Number of threads running non-I/O jobs in the processing thread pool. |`ProcessingPoolBusyNonIOThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Processing pool idle I/O job threads**<p><p>Number of idle threads for I/O jobs in the processing thread pool. |`ProcessingPoolIdleIOJobThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Processing pool idle non-I/O threads**<p><p>Number of idle threads in the processing thread pool dedicated to non-I/O jobs. |`ProcessingPoolIdleNonIOThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Processing pool I/O job queue length**<p><p>Number of I/O jobs in the queue of the processing thread pool. |`ProcessingPoolIOJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Processing Pool Job Queue Length**<p><p>Number of non-I/O jobs in the queue of the processing thread pool. |`ProcessingPoolJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**QPU**<p><p>QPU. Range 0-100 for S1, 0-200 for S2 and 0-400 for S4 |`qpu_metric` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Query Pool Busy Threads**<p><p>Number of busy threads in the query thread pool. |`QueryPoolBusyThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Query pool idle threads**<p><p>Number of idle threads for I/O jobs in the processing thread pool. |`QueryPoolIdleThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Query pool job queue lengt**<p><p>Number of jobs in the queue of the query thread pool. |`QueryPoolJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Quota**<p><p>Current memory quota, in bytes. Memory quota is also known as a memory grant or memory reservation. |`Quota` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Quota Blocked**<p><p>Current number of quota requests that are blocked until other memory quotas are freed. |`QuotaBlocked` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Processing: Rows converted per sec**<p><p>Rate of rows converted during processing. |`RowsConvertedPerSec` |CountPerSecond |Average |`ServerResourceType`|PT1M |Yes|
|**Processing: Rows read per sec**<p><p>Rate of rows read from all relational databases. |`RowsReadPerSec` |CountPerSecond |Average |`ServerResourceType`|PT1M |Yes|
|**Processing: Rows written per sec**<p><p>Rate of rows written during processing. |`RowsWrittenPerSec` |CountPerSecond |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Short parsing busy threads**<p><p>Number of busy threads in the short parsing thread pool. |`ShortParsingBusyThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Short parsing idle threads**<p><p>Number of idle threads in the short parsing thread pool. |`ShortParsingIdleThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Short parsing job queue length**<p><p>Number of jobs in the queue of the short parsing thread pool. |`ShortParsingJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Successful Connections Per Sec**<p><p>Rate of successful connection completions. |`SuccessfullConnectionsPerSec` |CountPerSecond |Average |`ServerResourceType`|PT1M |Yes|
|**Total Connection Failures**<p><p>Total failed connection attempts. |`TotalConnectionFailures` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Total Connection Requests**<p><p>Total connection requests. These are arrivals. |`TotalConnectionRequests` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: VertiPaq Nonpaged**<p><p>Bytes of memory locked in the working set for use by the in-memory engine. |`VertiPaqNonpaged` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: VertiPaq Paged**<p><p>Bytes of paged memory in use for in-memory data. |`VertiPaqPaged` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Virtual Bytes**<p><p>Virtual bytes. |`virtual_bytes_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|