---
title: Supported metrics - Microsoft.StorageCache/caches
description: Reference for Microsoft.StorageCache/caches metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.StorageCache/caches  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.StorageCache/caches resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Total Client IOPS<p><p>The rate of client file operations processed by the Cache. |`ClientIOPS` |Count |Average |No Dimensions |Yes|
|Average Client Latency<p><p>Average latency of client file operations to the Cache. |`ClientLatency` |MilliSeconds |Average |No Dimensions |Yes|
|Client Lock IOPS<p><p>Client file locking operations per second. |`ClientLockIOPS` |CountPerSecond |Average |No Dimensions |Yes|
|Client Metadata Read IOPS<p><p>The rate of client file operations sent to the Cache, excluding data reads, that do not modify persistent state. |`ClientMetadataReadIOPS` |CountPerSecond |Average |No Dimensions |Yes|
|Client Metadata Write IOPS<p><p>The rate of client file operations sent to the Cache, excluding data writes, that modify persistent state. |`ClientMetadataWriteIOPS` |CountPerSecond |Average |No Dimensions |Yes|
|Client Read IOPS<p><p>Client read operations per second. |`ClientReadIOPS` |CountPerSecond |Average |No Dimensions |Yes|
|Average Cache Read Throughput<p><p>Client read data transfer rate. |`ClientReadThroughput` |BytesPerSecond |Average |No Dimensions |Yes|
|Client Status<p><p>Client connection information. |`ClientStatus` |Count |Total |ClientSource, CacheAddress, ClientAddress, Protocol, ConnectionType |Yes|
|Client Write IOPS<p><p>Client write operations per second. |`ClientWriteIOPS` |CountPerSecond |Average |No Dimensions |Yes|
|Average Cache Write Throughput<p><p>Client write data transfer rate. |`ClientWriteThroughput` |BytesPerSecond |Average |No Dimensions |Yes|
|File Operations<p><p>Number of file operations per second. |`FileOps` |CountPerSecond |Average |SourceFile, Rank, FileType |Yes|
|File Reads<p><p>Number of bytes per second read from a file. |`FileReads` |BytesPerSecond |Average |SourceFile, Rank, FileType |Yes|
|File Updates<p><p>Number of directory updates and metadata operations per second. |`FileUpdates` |CountPerSecond |Average |SourceFile, Rank, FileType |Yes|
|File Writes<p><p>Number of bytes per second written to a file. |`FileWrites` |BytesPerSecond |Average |SourceFile, Rank, FileType |Yes|
|Storage Target Access Errors Received<p><p>The rate of access error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_ACCES). |`StorageTargetAccessErrors` |Count |Total |StorageTarget |Yes|
|StorageTarget Asynchronous Write Throughput<p><p>The rate the Cache asynchronously writes data to a particular StorageTarget. These are opportunistic writes that do not cause clients to block. |`StorageTargetAsyncWriteThroughput` |BytesPerSecond |Average |StorageTarget |Yes|
|Storage Target Blocks Recycled<p><p>Total number of 16k cache blocks recycled (freed) per Storage Target. |`StorageTargetBlocksRecycled` |Count |Average |StorageTarget |Yes|
|Storage Target File Too Large Errors Received<p><p>The rate of file too large error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_FBIG). |`StorageTargetFileTooLargeErrors` |Count |Total |StorageTarget |Yes|
|StorageTarget Fill Throughput<p><p>The rate the Cache reads data from the StorageTarget to handle a cache miss. |`StorageTargetFillThroughput` |BytesPerSecond |Average |StorageTarget |Yes|
|Storage Target Total Flush Failures<p><p>The rate of file flush request failures reported by the writeback state machine for a specific StorageTarget. |`StorageTargetFlushFailureErrors` |Count |Total |StorageTarget |Yes|
|Storage Target Free Read Space<p><p>Read space available for caching files associated with a storage target. |`StorageTargetFreeReadSpace` |Bytes |Average |StorageTarget |Yes|
|Storage Target Free Write Space<p><p>Write space available for changed files associated with a storage target. |`StorageTargetFreeWriteSpace` |Bytes |Average |StorageTarget |Yes|
|Storage Target Health<p><p>Boolean results of connectivity test between the Cache and Storage Targets. |`StorageTargetHealth` |Count |Average |No Dimensions |Yes|
|Total StorageTarget IOPS<p><p>The rate of all file operations the Cache sends to a particular StorageTarget. |`StorageTargetIOPS` |Count |Average |StorageTarget |Yes|
|StorageTarget Latency<p><p>The average round trip latency of all the file operations the Cache sends to a partricular StorageTarget. |`StorageTargetLatency` |MilliSeconds |Average |StorageTarget |Yes|
|StorageTarget Metadata Read IOPS<p><p>The rate of file operations that do not modify persistent state, and excluding the read operation, that the Cache sends to a particular StorageTarget. |`StorageTargetMetadataReadIOPS` |CountPerSecond |Average |StorageTarget |Yes|
|StorageTarget Metadata Write IOPS<p><p>The rate of file operations that do modify persistent state and excluding the write operation, that the Cache sends to a particular StorageTarget. |`StorageTargetMetadataWriteIOPS` |CountPerSecond |Average |StorageTarget |Yes|
|Storage Target No Space Errors Received<p><p>The rate of no space available error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_NOSPC). |`StorageTargetNoSpaceErrors` |Count |Total |StorageTarget |Yes|
|Storage Target Permission Errors Received<p><p>The rate of permission error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_PERM). |`StorageTargetPermissionErrors` |Count |Total |StorageTarget |Yes|
|Storage Target Quota Limit Errors Received<p><p>The rate of quota limit error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_DQUOT). |`StorageTargetQuotaLimitErrors` |Count |Total |StorageTarget |Yes|
|StorageTarget Read Ahead Throughput<p><p>The rate the Cache opportunisticly reads data from the StorageTarget. |`StorageTargetReadAheadThroughput` |BytesPerSecond |Average |StorageTarget |Yes|
|StorageTarget Read IOPS<p><p>The rate of file read operations the Cache sends to a particular StorageTarget. |`StorageTargetReadIOPS` |CountPerSecond |Average |StorageTarget |Yes|
|Storage Target Read-Only Filesystem Errors Received<p><p>The rate of read-only filesystem error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_ROFS). |`StorageTargetReadOnlyErrors` |Count |Total |StorageTarget |Yes|
|Storage Target Recycle Rate<p><p>Cache space recycle rate associated with a storage target in the HPC Cache. This is the rate at which existing data is cleared from the cache to make room for new data. |`StorageTargetRecycleRate` |BytesPerSecond |Average |StorageTarget |Yes|
|Storage Target Request Too Small Errors Received<p><p>The rate of request too small error responses received by the cache from a specific StorageTarget. For more details, see https://www.rfc-editor.org/rfc/rfc1813#section-2.6 (NFS3ERR_TOOSMALL). |`StorageTargetRequestTooSmallErrors` |Count |Total |StorageTarget |Yes|
|Storage Target Retryable Flush Request Errors<p><p>The rate of retryable file flush errors reported by the writeback state machine for a specific StorageTarget. |`StorageTargetRetryableFlushErrors` |Count |Total |StorageTarget |Yes|
|Storage Target Space Allocation<p><p>Total space (read and write) allocated for a storage target. |`StorageTargetSpaceAllocation` |Bytes |Average |StorageTarget |Yes|
|StorageTarget Synchronous Write Throughput<p><p>The rate the Cache synchronously writes data to a particular StorageTarget. These are writes that do cause clients to block. |`StorageTargetSyncWriteThroughput` |BytesPerSecond |Average |StorageTarget |Yes|
|Storage Target Total Cache Ops<p><p>The rate of operations the cache is servicing for the namespace represented by a specific StorageTarget. |`StorageTargetTotalCacheOps` |Count |Total |StorageTarget |Yes|
|Storage Target Total Read Space<p><p>Total read space allocated for caching files associated with a storage target. |`StorageTargetTotalReadSpace` |Bytes |Average |StorageTarget |Yes|
|StorageTarget Total Read Throughput<p><p>The total rate that the Cache reads data from a particular StorageTarget. |`StorageTargetTotalReadThroughput` |BytesPerSecond |Average |StorageTarget |Yes|
|Storage Target Total Write Space<p><p>Total write space allocated for changed files associated with a storage target. |`StorageTargetTotalWriteSpace` |Bytes |Average |StorageTarget |Yes|
|StorageTarget Total Write Throughput<p><p>The total rate that the Cache writes data to a particular StorageTarget. |`StorageTargetTotalWriteThroughput` |BytesPerSecond |Average |StorageTarget |Yes|
|Storage Target Uncoverable Flush Request Errors<p><p>The rate of unrecoverable file flush errors reported by the writeback state machine for a specific StorageTarget. |`StorageTargetUnrecoverableFlushErrors` |Count |Total |StorageTarget |Yes|
|Storage Target Update Found Asynchronous Verification Cache Ops<p><p>The rate of file updates discovered by asynchronous verification operations sent by the cache to a specific StorageTarget. |`StorageTargetUpdateFoundAsyncCacheOps` |Count |Total |StorageTarget |Yes|
|Storage Target Update Found Synchronous Verification Cache Ops<p><p>The rate of file updates discovered by synchronous verification operations sent by the cache to a specific StorageTarget. |`StorageTargetUpdateFoundSyncCacheOps` |Count |Total |StorageTarget |Yes|
|Storage Target Used Read Space<p><p>Read space used by cached files associated with a storage target. |`StorageTargetUsedReadSpace` |Bytes |Average |StorageTarget |Yes|
|Storage Target Used Write Space<p><p>Write space used by changed files associated with a storage target. |`StorageTargetUsedWriteSpace` |Bytes |Average |StorageTarget |Yes|
|Storage Target Asynchronous Verification Cache Ops<p><p>The rate of asynchronous verification operations sent by the cache to a specific StorageTarget. |`StorageTargetVerificationAsyncCacheOps` |Count |Total |StorageTarget |Yes|
|Storage Target Synchronous Verification Cache Ops<p><p>The rate of synchronous verification operations sent by the cache to a specific StorageTarget. |`StorageTargetVerificationSyncCacheOps` |Count |Total |StorageTarget |Yes|
|StorageTarget Write IOPS<p><p>The rate of the file write operations the Cache sends to a particular StorageTarget. |`StorageTargetWriteIOPS` |Count |Average |StorageTarget |Yes|
|Total Blocks Recycled<p><p>Total number of 16k cache blocks recycled (freed) for the HPC Cache. |`TotalBlocksRecycled` |Count |Average |No Dimensions |Yes|
|Free Read Space<p><p>Total space available for caching read files. |`TotalFreeReadSpace` |Bytes |Average |No Dimensions |Yes|
|Free Write Read Space<p><p>Total write space available to store changed data in the cache. |`TotalFreeWriteSpace` |Bytes |Average |No Dimensions |Yes|
|Recycle Rate<p><p>Total cache space recycle rate in the HPC Cache. This is the rate at which existing data is cleared from the cache to make room for new data. |`TotalRecycleRate` |BytesPerSecond |Average |No Dimensions |Yes|
|Used Read Space<p><p>Total read space used by changed files for the HPC Cache. |`TotalUsedReadSpace` |Bytes |Average |No Dimensions |Yes|
|Used Write Space<p><p>Total write space used by changed files for the HPC Cache. |`TotalUsedWriteSpace` |Bytes |Average |No Dimensions |Yes|
|Uptime<p><p>Boolean results of connectivity test between the Cache and monitoring system. |`Uptime` |Count |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->