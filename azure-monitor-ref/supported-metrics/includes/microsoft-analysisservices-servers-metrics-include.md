---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.AnalysisServices/servers, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Memory: Cleaner Current Price**<br><br>Current price of memory, $/byte/time, normalized to 1000. |`CleanerCurrentPrice` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Cleaner Memory nonshrinkable**<br><br>Amount of memory, in bytes, not subject to purging by the background cleaner. |`CleanerMemoryNonshrinkable` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Cleaner Memory shrinkable**<br><br>Amount of memory, in bytes, subject to purging by the background cleaner. |`CleanerMemoryShrinkable` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Command pool busy threads**<br><br>Number of busy threads in the command thread pool. |`CommandPoolBusyThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Command pool idle threads**<br><br>Number of idle threads in the command thread pool. |`CommandPoolIdleThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Command Pool Job Queue Length**<br><br>Number of jobs in the queue of the command thread pool. |`CommandPoolJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Connection: Current connections**<br><br>Current number of client connections established. |`CurrentConnections` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Current User Sessions**<br><br>Current number of user sessions established. |`CurrentUserSessions` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Long parsing busy threads**<br><br>Number of busy threads in the long parsing thread pool. |`LongParsingBusyThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Long parsing idle threads**<br><br>Number of idle threads in the long parsing thread pool. |`LongParsingIdleThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Long parsing job queue length**<br><br>Number of jobs in the queue of the long parsing thread pool. |`LongParsingJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**M Engine Memory**<br><br>Memory usage by mashup engine processes |`mashup_engine_memory_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**M Engine Private Bytes**<br><br>Private bytes usage by mashup engine processes. |`mashup_engine_private_bytes_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**M Engine QPU**<br><br>QPU usage by mashup engine processes |`mashup_engine_qpu_metric` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**M Engine Virtual Bytes**<br><br>Virtual bytes usage by mashup engine processes. |`mashup_engine_virtual_bytes_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory**<br><br>Memory. Range 0-25 GB for S1, 0-50 GB for S2 and 0-100 GB for S4 |`memory_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory Thrashing**<br><br>Average memory thrashing. |`memory_thrashing_metric` |Percent |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Memory Limit Hard**<br><br>Hard memory limit, from configuration file. |`MemoryLimitHard` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Memory Limit High**<br><br>High memory limit, from configuration file. |`MemoryLimitHigh` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Memory Limit Low**<br><br>Low memory limit, from configuration file. |`MemoryLimitLow` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Memory Limit VertiPaq**<br><br>In-memory limit, from configuration file. |`MemoryLimitVertiPaq` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Memory Usage**<br><br>Memory usage of the server process as used in calculating cleaner memory price. Equal to counter Process\PrivateBytes plus the size of memory-mapped data, ignoring any memory which was mapped or allocated by the xVelocity in-memory analytics engine (VertiPaq) in excess of the xVelocity engine Memory Limit. |`MemoryUsage` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Private Bytes**<br><br>Private bytes. |`private_bytes_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Processing pool busy I/O job threads**<br><br>Number of threads running I/O jobs in the processing thread pool. |`ProcessingPoolBusyIOJobThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Processing pool busy non-I/O threads**<br><br>Number of threads running non-I/O jobs in the processing thread pool. |`ProcessingPoolBusyNonIOThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Processing pool idle I/O job threads**<br><br>Number of idle threads for I/O jobs in the processing thread pool. |`ProcessingPoolIdleIOJobThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Processing pool idle non-I/O threads**<br><br>Number of idle threads in the processing thread pool dedicated to non-I/O jobs. |`ProcessingPoolIdleNonIOThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Processing pool I/O job queue length**<br><br>Number of I/O jobs in the queue of the processing thread pool. |`ProcessingPoolIOJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Processing Pool Job Queue Length**<br><br>Number of non-I/O jobs in the queue of the processing thread pool. |`ProcessingPoolJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**QPU**<br><br>QPU. Range 0-100 for S1, 0-200 for S2 and 0-400 for S4 |`qpu_metric` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Query Pool Busy Threads**<br><br>Number of busy threads in the query thread pool. |`QueryPoolBusyThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Query pool idle threads**<br><br>Number of idle threads for I/O jobs in the processing thread pool. |`QueryPoolIdleThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Query pool job queue lengt**<br><br>Number of jobs in the queue of the query thread pool. |`QueryPoolJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Quota**<br><br>Current memory quota, in bytes. Memory quota is also known as a memory grant or memory reservation. |`Quota` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: Quota Blocked**<br><br>Current number of quota requests that are blocked until other memory quotas are freed. |`QuotaBlocked` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Processing: Rows converted per sec**<br><br>Rate of rows converted during processing. |`RowsConvertedPerSec` |CountPerSecond |Average |`ServerResourceType`|PT1M |Yes|
|**Processing: Rows read per sec**<br><br>Rate of rows read from all relational databases. |`RowsReadPerSec` |CountPerSecond |Average |`ServerResourceType`|PT1M |Yes|
|**Processing: Rows written per sec**<br><br>Rate of rows written during processing. |`RowsWrittenPerSec` |CountPerSecond |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Short parsing busy threads**<br><br>Number of busy threads in the short parsing thread pool. |`ShortParsingBusyThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Short parsing idle threads**<br><br>Number of idle threads in the short parsing thread pool. |`ShortParsingIdleThreads` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Threads: Short parsing job queue length**<br><br>Number of jobs in the queue of the short parsing thread pool. |`ShortParsingJobQueueLength` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Successful Connections Per Sec**<br><br>Rate of successful connection completions. |`SuccessfullConnectionsPerSec` |CountPerSecond |Average |`ServerResourceType`|PT1M |Yes|
|**Total Connection Failures**<br><br>Total failed connection attempts. |`TotalConnectionFailures` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Total Connection Requests**<br><br>Total connection requests. These are arrivals. |`TotalConnectionRequests` |Count |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: VertiPaq Nonpaged**<br><br>Bytes of memory locked in the working set for use by the in-memory engine. |`VertiPaqNonpaged` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Memory: VertiPaq Paged**<br><br>Bytes of paged memory in use for in-memory data. |`VertiPaqPaged` |Bytes |Average |`ServerResourceType`|PT1M |Yes|
|**Virtual Bytes**<br><br>Virtual bytes. |`virtual_bytes_metric` |Bytes |Average |`ServerResourceType`|PT1M |Yes|