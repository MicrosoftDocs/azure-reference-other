---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.StorageCache/caches, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Total Client IOPS**<br><br>The rate of client file operations processed by the Cache. |`ClientIOPS` |Count |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Average Client Latency**<br><br>Average latency of client file operations to the Cache. |`ClientLatency` |MilliSeconds |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Client Lock IOPS**<br><br>Client file locking operations per second. |`ClientLockIOPS` |CountPerSecond |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Client Metadata Read IOPS**<br><br>The rate of client file operations sent to the Cache, excluding data reads, that do not modify persistent state. |`ClientMetadataReadIOPS` |CountPerSecond |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Client Metadata Write IOPS**<br><br>The rate of client file operations sent to the Cache, excluding data writes, that modify persistent state. |`ClientMetadataWriteIOPS` |CountPerSecond |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Client Read IOPS**<br><br>Client read operations per second. |`ClientReadIOPS` |CountPerSecond |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Average Cache Read Throughput**<br><br>Client read data transfer rate. |`ClientReadThroughput` |BytesPerSecond |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Client Status**<br><br>Client connection information. |`ClientStatus` |Count |Total |`ClientSource`, `CacheAddress`, `ClientAddress`, `Protocol`, `ConnectionType`|PT1M |Yes|
|**Client Write IOPS**<br><br>Client write operations per second. |`ClientWriteIOPS` |CountPerSecond |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Average Cache Write Throughput**<br><br>Client write data transfer rate. |`ClientWriteThroughput` |BytesPerSecond |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**File Operations**<br><br>Number of file operations per second. |`FileOps` |CountPerSecond |Minimum, Maximum, Average |`SourceFile`, `Rank`, `FileType`|PT1M |Yes|
|**File Reads**<br><br>Number of bytes per second read from a file. |`FileReads` |BytesPerSecond |Minimum, Maximum, Average |`SourceFile`, `Rank`, `FileType`|PT1M |Yes|
|**File Updates**<br><br>Number of directory updates and metadata operations per second. |`FileUpdates` |CountPerSecond |Minimum, Maximum, Average |`SourceFile`, `Rank`, `FileType`|PT1M |Yes|
|**File Writes**<br><br>Number of bytes per second written to a file. |`FileWrites` |BytesPerSecond |Minimum, Maximum, Average |`SourceFile`, `Rank`, `FileType`|PT1M |Yes|
|**Storage Target Access Errors Received**<br><br>The rate of access error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_ACCES). |`StorageTargetAccessErrors` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**StorageTarget Asynchronous Write Throughput**<br><br>The rate the Cache asynchronously writes data to a particular StorageTarget. These are opportunistic writes that do not cause clients to block. |`StorageTargetAsyncWriteThroughput` |BytesPerSecond |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Blocks Recycled**<br><br>Total number of 16k cache blocks recycled (freed) per Storage Target. |`StorageTargetBlocksRecycled` |Count |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target File Too Large Errors Received**<br><br>The rate of file too large error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_FBIG). |`StorageTargetFileTooLargeErrors` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**StorageTarget Fill Throughput**<br><br>The rate the Cache reads data from the StorageTarget to handle a cache miss. |`StorageTargetFillThroughput` |BytesPerSecond |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Total Flush Failures**<br><br>The rate of file flush request failures reported by the writeback state machine for a specific StorageTarget. |`StorageTargetFlushFailureErrors` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Free Read Space**<br><br>Read space available for caching files associated with a storage target. |`StorageTargetFreeReadSpace` |Bytes |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Free Write Space**<br><br>Write space available for changed files associated with a storage target. |`StorageTargetFreeWriteSpace` |Bytes |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Health**<br><br>Boolean results of connectivity test between the Cache and Storage Targets. |`StorageTargetHealth` |Count |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Total StorageTarget IOPS**<br><br>The rate of all file operations the Cache sends to a particular StorageTarget. |`StorageTargetIOPS` |Count |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**StorageTarget Latency**<br><br>The average round trip latency of all the file operations the Cache sends to a partricular StorageTarget. |`StorageTargetLatency` |MilliSeconds |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**StorageTarget Metadata Read IOPS**<br><br>The rate of file operations that do not modify persistent state, and excluding the read operation, that the Cache sends to a particular StorageTarget. |`StorageTargetMetadataReadIOPS` |CountPerSecond |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**StorageTarget Metadata Write IOPS**<br><br>The rate of file operations that do modify persistent state and excluding the write operation, that the Cache sends to a particular StorageTarget. |`StorageTargetMetadataWriteIOPS` |CountPerSecond |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target No Space Errors Received**<br><br>The rate of no space available error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_NOSPC). |`StorageTargetNoSpaceErrors` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Permission Errors Received**<br><br>The rate of permission error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_PERM). |`StorageTargetPermissionErrors` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Quota Limit Errors Received**<br><br>The rate of quota limit error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_DQUOT). |`StorageTargetQuotaLimitErrors` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**StorageTarget Read Ahead Throughput**<br><br>The rate the Cache opportunisticly reads data from the StorageTarget. |`StorageTargetReadAheadThroughput` |BytesPerSecond |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**StorageTarget Read IOPS**<br><br>The rate of file read operations the Cache sends to a particular StorageTarget. |`StorageTargetReadIOPS` |CountPerSecond |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Read-Only Filesystem Errors Received**<br><br>The rate of read-only filesystem error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_ROFS). |`StorageTargetReadOnlyErrors` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Recycle Rate**<br><br>Cache space recycle rate associated with a storage target in the HPC Cache. This is the rate at which existing data is cleared from the cache to make room for new data. |`StorageTargetRecycleRate` |BytesPerSecond |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Request Too Small Errors Received**<br><br>The rate of request too small error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_TOOSMALL). |`StorageTargetRequestTooSmallErrors` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Retryable Flush Request Errors**<br><br>The rate of retryable file flush errors reported by the writeback state machine for a specific StorageTarget. |`StorageTargetRetryableFlushErrors` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Space Allocation**<br><br>Total space (read and write) allocated for a storage target. |`StorageTargetSpaceAllocation` |Bytes |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**StorageTarget Synchronous Write Throughput**<br><br>The rate the Cache synchronously writes data to a particular StorageTarget. These are writes that do cause clients to block. |`StorageTargetSyncWriteThroughput` |BytesPerSecond |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Total Cache Ops**<br><br>The rate of operations the cache is servicing for the namespace represented by a specific StorageTarget. |`StorageTargetTotalCacheOps` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Total Read Space**<br><br>Total read space allocated for caching files associated with a storage target. |`StorageTargetTotalReadSpace` |Bytes |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**StorageTarget Total Read Throughput**<br><br>The total rate that the Cache reads data from a particular StorageTarget. |`StorageTargetTotalReadThroughput` |BytesPerSecond |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Total Write Space**<br><br>Total write space allocated for changed files associated with a storage target. |`StorageTargetTotalWriteSpace` |Bytes |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**StorageTarget Total Write Throughput**<br><br>The total rate that the Cache writes data to a particular StorageTarget. |`StorageTargetTotalWriteThroughput` |BytesPerSecond |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Uncoverable Flush Request Errors**<br><br>The rate of unrecoverable file flush errors reported by the writeback state machine for a specific StorageTarget. |`StorageTargetUnrecoverableFlushErrors` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Update Found Asynchronous Verification Cache Ops**<br><br>The rate of file updates discovered by asynchronous verification operations sent by the cache to a specific StorageTarget. |`StorageTargetUpdateFoundAsyncCacheOps` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Update Found Synchronous Verification Cache Ops**<br><br>The rate of file updates discovered by synchronous verification operations sent by the cache to a specific StorageTarget. |`StorageTargetUpdateFoundSyncCacheOps` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Used Read Space**<br><br>Read space used by cached files associated with a storage target. |`StorageTargetUsedReadSpace` |Bytes |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Used Write Space**<br><br>Write space used by changed files associated with a storage target. |`StorageTargetUsedWriteSpace` |Bytes |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Storage Target Asynchronous Verification Cache Ops**<br><br>The rate of asynchronous verification operations sent by the cache to a specific StorageTarget. |`StorageTargetVerificationAsyncCacheOps` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**Storage Target Synchronous Verification Cache Ops**<br><br>The rate of synchronous verification operations sent by the cache to a specific StorageTarget. |`StorageTargetVerificationSyncCacheOps` |Count |Minimum, Maximum, Average, Total |`StorageTarget`|PT1M |Yes|
|**StorageTarget Write IOPS**<br><br>The rate of the file write operations the Cache sends to a particular StorageTarget. |`StorageTargetWriteIOPS` |Count |Minimum, Maximum, Average |`StorageTarget`|PT1M |Yes|
|**Total Blocks Recycled**<br><br>Total number of 16k cache blocks recycled (freed) for the HPC Cache. |`TotalBlocksRecycled` |Count |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Free Read Space**<br><br>Total space available for caching read files. |`TotalFreeReadSpace` |Bytes |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Free Write Read Space**<br><br>Total write space available to store changed data in the cache. |`TotalFreeWriteSpace` |Bytes |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Recycle Rate**<br><br>Total cache space recycle rate in the HPC Cache. This is the rate at which existing data is cleared from the cache to make room for new data. |`TotalRecycleRate` |BytesPerSecond |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Used Read Space**<br><br>Total read space used by changed files for the HPC Cache. |`TotalUsedReadSpace` |Bytes |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Used Write Space**<br><br>Total write space used by changed files for the HPC Cache. |`TotalUsedWriteSpace` |Bytes |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|**Uptime**<br><br>Boolean results of connectivity test between the Cache and monitoring system. |`Uptime` |Count |Minimum, Maximum, Average |\<none\>|PT1M |Yes|