---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/02/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Cache/redis, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Cache Hits (Instance Based)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`allcachehits` |Count |Total |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Cache Misses (Instance Based)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`allcachemisses` |Count |Total |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Cache Read (Instance Based)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`allcacheRead` |BytesPerSecond |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Cache Write (Instance Based)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`allcacheWrite` |BytesPerSecond |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Connected Clients (Instance Based)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`allconnectedclients` |Count |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Connections Closed Per Second (Instance Based)**<p><p>The number of instantaneous connections closed per second on the cache via port 6379 or 6380 (SSL). For more details, see https://aka.ms/redis/metrics. |`allConnectionsClosedPerSecond` |CountPerSecond |Average, Minimum, Maximum, Count |`ShardId`, `Primary`, `Ssl`|PT1M |Yes|
|**Connections Created Per Second (Instance Based)**<p><p>The number of instantaneous connections created per second on the cache via port 6379 or 6380 (SSL). For more details, see https://aka.ms/redis/metrics. |`allConnectionsCreatedPerSecond` |CountPerSecond |Average, Minimum, Maximum, Count |`ShardId`, `Primary`, `Ssl`|PT1M |Yes|
|**Evicted Keys (Instance Based)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`allevictedkeys` |Count |Total |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Expired Keys (Instance Based)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`allexpiredkeys` |Count |Total |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Gets (Instance Based)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`allgetcommands` |Count |Total |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Operations Per Second (Instance Based)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`alloperationsPerSecond` |Count |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**CPU (Instance Based)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`allpercentprocessortime` |Percent |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Server Load (Instance Based)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`allserverLoad` |Percent |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Sets (Instance Based)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`allsetcommands` |Count |Total |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Total Operations  (Instance Based)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`alltotalcommandsprocessed` |Count |Total |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Total Keys (Instance Based)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`alltotalkeys` |Count |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Used Memory (Instance Based)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`allusedmemory` |Bytes |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Used Memory Percentage (Instance Based)**<p><p>The percentage of cache memory used for key/value pairs. For more details, see https://aka.ms/redis/metrics. |`allusedmemorypercentage` |Percent |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Used Memory RSS (Instance Based)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`allusedmemoryRss` |Bytes |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Cache Hits**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits` |Count |Total |`ShardId`|PT1M |Yes|
|**Cache Hits (Shard 0)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits0` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Hits (Shard 1)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits1` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Hits (Shard 2)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits2` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Hits (Shard 3)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits3` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Hits (Shard 4)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits4` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Hits (Shard 5)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits5` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Hits (Shard 6)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits6` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Hits (Shard 7)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits7` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Hits (Shard 8)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits8` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Hits (Shard 9)**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/metrics. |`cachehits9` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Latency Microseconds (Preview)**<p><p>The latency to the cache in microseconds. For more details, see https://aka.ms/redis/metrics. |`cacheLatency` |Count |Average |`ShardId`|PT1M |Yes|
|**Cache Misses**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses` |Count |Total |`ShardId`|PT1M |Yes|
|**Cache Misses (Shard 0)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses0` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Misses (Shard 1)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses1` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Misses (Shard 2)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses2` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Misses (Shard 3)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses3` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Misses (Shard 4)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses4` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Misses (Shard 5)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses5` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Misses (Shard 6)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses6` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Misses (Shard 7)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses7` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Misses (Shard 8)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses8` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Misses (Shard 9)**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/metrics. |`cachemisses9` |Count |Total |\<none\>|PT1M |Yes|
|**Cache Miss Rate**<p><p>The % of get requests that miss. For more details, see https://aka.ms/redis/metrics. |`cachemissrate` |Percent |Total |`ShardId`|PT1M |Yes|
|**Cache Read**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead` |BytesPerSecond |Maximum |`ShardId`|PT1M |Yes|
|**Cache Read (Shard 0)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead0` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Read (Shard 1)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead1` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Read (Shard 2)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead2` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Read (Shard 3)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead3` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Read (Shard 4)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead4` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Read (Shard 5)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead5` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Read (Shard 6)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead6` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Read (Shard 7)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead7` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Read (Shard 8)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead8` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Read (Shard 9)**<p><p>The amount of data read from the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheRead9` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Write**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite` |BytesPerSecond |Maximum |`ShardId`|PT1M |Yes|
|**Cache Write (Shard 0)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite0` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Write (Shard 1)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite1` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Write (Shard 2)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite2` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Write (Shard 3)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite3` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Write (Shard 4)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite4` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Write (Shard 5)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite5` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Write (Shard 6)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite6` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Write (Shard 7)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite7` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Write (Shard 8)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite8` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Cache Write (Shard 9)**<p><p>The amount of data written to the cache in bytes per second. For more details, see https://aka.ms/redis/metrics. |`cacheWrite9` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients` |Count |Maximum |`ShardId`|PT1M |Yes|
|**Connected Clients (Shard 0)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients0` |Count |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients (Shard 1)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients1` |Count |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients (Shard 2)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients2` |Count |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients (Shard 3)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients3` |Count |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients (Shard 4)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients4` |Count |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients (Shard 5)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients5` |Count |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients (Shard 6)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients6` |Count |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients (Shard 7)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients7` |Count |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients (Shard 8)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients8` |Count |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients (Shard 9)**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/metrics. |`connectedclients9` |Count |Maximum |\<none\>|PT1M |Yes|
|**Connected Clients using Microsoft Entra Token (Instance Based)**<p><p>The number of client connections to the cache using Microsoft Entra Token. For more details, see https://aka.ms/redis/metrics. |`ConnectedClientsUsingAADToken` |Count |Maximum |`ShardId`, `Port`, `Primary`|PT1M |Yes|
|**Errors**<p><p>The number errors that occured on the cache. For more details, see https://aka.ms/redis/metrics. |`errors` |Count |Maximum |`ShardId`, `ErrorType`|PT1M |Yes|
|**Evicted Keys**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys` |Count |Total |`ShardId`|PT1M |Yes|
|**Evicted Keys (Shard 0)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys0` |Count |Total |\<none\>|PT1M |Yes|
|**Evicted Keys (Shard 1)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys1` |Count |Total |\<none\>|PT1M |Yes|
|**Evicted Keys (Shard 2)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys2` |Count |Total |\<none\>|PT1M |Yes|
|**Evicted Keys (Shard 3)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys3` |Count |Total |\<none\>|PT1M |Yes|
|**Evicted Keys (Shard 4)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys4` |Count |Total |\<none\>|PT1M |Yes|
|**Evicted Keys (Shard 5)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys5` |Count |Total |\<none\>|PT1M |Yes|
|**Evicted Keys (Shard 6)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys6` |Count |Total |\<none\>|PT1M |Yes|
|**Evicted Keys (Shard 7)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys7` |Count |Total |\<none\>|PT1M |Yes|
|**Evicted Keys (Shard 8)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys8` |Count |Total |\<none\>|PT1M |Yes|
|**Evicted Keys (Shard 9)**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/metrics. |`evictedkeys9` |Count |Total |\<none\>|PT1M |Yes|
|**Expired Keys**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys` |Count |Total |`ShardId`|PT1M |Yes|
|**Expired Keys (Shard 0)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys0` |Count |Total |\<none\>|PT1M |Yes|
|**Expired Keys (Shard 1)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys1` |Count |Total |\<none\>|PT1M |Yes|
|**Expired Keys (Shard 2)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys2` |Count |Total |\<none\>|PT1M |Yes|
|**Expired Keys (Shard 3)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys3` |Count |Total |\<none\>|PT1M |Yes|
|**Expired Keys (Shard 4)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys4` |Count |Total |\<none\>|PT1M |Yes|
|**Expired Keys (Shard 5)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys5` |Count |Total |\<none\>|PT1M |Yes|
|**Expired Keys (Shard 6)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys6` |Count |Total |\<none\>|PT1M |Yes|
|**Expired Keys (Shard 7)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys7` |Count |Total |\<none\>|PT1M |Yes|
|**Expired Keys (Shard 8)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys8` |Count |Total |\<none\>|PT1M |Yes|
|**Expired Keys (Shard 9)**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/metrics. |`expiredkeys9` |Count |Total |\<none\>|PT1M |Yes|
|**Geo-replication Connectivity Lag**<p><p>Time in seconds since last successful data synchronization with geo-primary cache. Value will continue to increase if the link status is down. For more details, see https://aka.ms/redis/georeplicationmetrics. |`GeoReplicationConnectivityLag` |Seconds |Average, Minimum, Maximum |`ShardId`|PT1M |Yes|
|**Geo-replication Data Sync Offset**<p><p>Approximate amount of data in bytes that needs to be synchronized to geo-secondary cache. For more details, see https://aka.ms/redis/georeplicationmetrics. |`GeoReplicationDataSyncOffset` |Bytes |Average, Minimum, Maximum |`ShardId`|PT1M |Yes|
|**Geo-replication Full Sync Event Finished**<p><p>Fired on completion of a full synchronization event between geo-replicated caches. This metric reports 0 most of the time because geo-replication uses partial resynchronizations for any new data added after the initial full synchronization. For more details, see https://aka.ms/redis/georeplicationmetrics. |`GeoReplicationFullSyncEventFinished` |Count |Count |`ShardId`|PT1M |Yes|
|**Geo-replication Full Sync Event Started**<p><p>Fired on initiation of a full synchronization event between geo-replicated caches. This metric reports 0 most of the time because geo-replication uses partial resynchronizations for any new data added after the initial full synchronization. For more details, see https://aka.ms/redis/georeplicationmetrics. |`GeoReplicationFullSyncEventStarted` |Count |Count |`ShardId`|PT1M |Yes|
|**Geo-replication Healthy**<p><p>The health status of geo-replication link. 1 if healthy and 0 if disconnected or unhealthy. For more details, see https://aka.ms/redis/georeplicationmetrics. |`GeoReplicationHealthy` |Count |Average, Minimum, Maximum |`ShardId`|PT1M |Yes|
|**Gets**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands` |Count |Total |`ShardId`|PT1M |Yes|
|**Gets (Shard 0)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands0` |Count |Total |\<none\>|PT1M |Yes|
|**Gets (Shard 1)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands1` |Count |Total |\<none\>|PT1M |Yes|
|**Gets (Shard 2)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands2` |Count |Total |\<none\>|PT1M |Yes|
|**Gets (Shard 3)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands3` |Count |Total |\<none\>|PT1M |Yes|
|**Gets (Shard 4)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands4` |Count |Total |\<none\>|PT1M |Yes|
|**Gets (Shard 5)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands5` |Count |Total |\<none\>|PT1M |Yes|
|**Gets (Shard 6)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands6` |Count |Total |\<none\>|PT1M |Yes|
|**Gets (Shard 7)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands7` |Count |Total |\<none\>|PT1M |Yes|
|**Gets (Shard 8)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands8` |Count |Total |\<none\>|PT1M |Yes|
|**Gets (Shard 9)**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/metrics. |`getcommands9` |Count |Total |\<none\>|PT1M |Yes|
|**99th percentile latency**<p><p>Measures the worst-case (99th percentile) latency of server-side commands in microseconds. Measured by issuing PING commands from the load balancer to the Redis server and tracking the time to respond. |`LatencyP99` |Count |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Operations Per Second**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond` |Count |Maximum |`ShardId`|PT1M |Yes|
|**Operations Per Second (Shard 0)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond0` |Count |Maximum |\<none\>|PT1M |Yes|
|**Operations Per Second (Shard 1)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond1` |Count |Maximum |\<none\>|PT1M |Yes|
|**Operations Per Second (Shard 2)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond2` |Count |Maximum |\<none\>|PT1M |Yes|
|**Operations Per Second (Shard 3)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond3` |Count |Maximum |\<none\>|PT1M |Yes|
|**Operations Per Second (Shard 4)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond4` |Count |Maximum |\<none\>|PT1M |Yes|
|**Operations Per Second (Shard 5)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond5` |Count |Maximum |\<none\>|PT1M |Yes|
|**Operations Per Second (Shard 6)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond6` |Count |Maximum |\<none\>|PT1M |Yes|
|**Operations Per Second (Shard 7)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond7` |Count |Maximum |\<none\>|PT1M |Yes|
|**Operations Per Second (Shard 8)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond8` |Count |Maximum |\<none\>|PT1M |Yes|
|**Operations Per Second (Shard 9)**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/metrics. |`operationsPerSecond9` |Count |Maximum |\<none\>|PT1M |Yes|
|**CPU**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime` |Percent |Maximum |`ShardId`|PT1M |Yes|
|**CPU (Shard 0)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime0` |Percent |Maximum |\<none\>|PT1M |Yes|
|**CPU (Shard 1)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime1` |Percent |Maximum |\<none\>|PT1M |Yes|
|**CPU (Shard 2)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime2` |Percent |Maximum |\<none\>|PT1M |Yes|
|**CPU (Shard 3)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime3` |Percent |Maximum |\<none\>|PT1M |Yes|
|**CPU (Shard 4)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime4` |Percent |Maximum |\<none\>|PT1M |Yes|
|**CPU (Shard 5)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime5` |Percent |Maximum |\<none\>|PT1M |Yes|
|**CPU (Shard 6)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime6` |Percent |Maximum |\<none\>|PT1M |Yes|
|**CPU (Shard 7)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime7` |Percent |Maximum |\<none\>|PT1M |Yes|
|**CPU (Shard 8)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime8` |Percent |Maximum |\<none\>|PT1M |Yes|
|**CPU (Shard 9)**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/metrics. |`percentProcessorTime9` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Server Load**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad` |Percent |Maximum |`ShardId`|PT1M |Yes|
|**Server Load (Shard 0)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad0` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Server Load (Shard 1)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad1` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Server Load (Shard 2)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad2` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Server Load (Shard 3)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad3` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Server Load (Shard 4)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad4` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Server Load (Shard 5)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad5` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Server Load (Shard 6)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad6` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Server Load (Shard 7)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad7` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Server Load (Shard 8)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad8` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Server Load (Shard 9)**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/metrics. |`serverLoad9` |Percent |Maximum |\<none\>|PT1M |Yes|
|**Sets**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands` |Count |Total |`ShardId`|PT1M |Yes|
|**Sets (Shard 0)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands0` |Count |Total |\<none\>|PT1M |Yes|
|**Sets (Shard 1)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands1` |Count |Total |\<none\>|PT1M |Yes|
|**Sets (Shard 2)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands2` |Count |Total |\<none\>|PT1M |Yes|
|**Sets (Shard 3)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands3` |Count |Total |\<none\>|PT1M |Yes|
|**Sets (Shard 4)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands4` |Count |Total |\<none\>|PT1M |Yes|
|**Sets (Shard 5)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands5` |Count |Total |\<none\>|PT1M |Yes|
|**Sets (Shard 6)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands6` |Count |Total |\<none\>|PT1M |Yes|
|**Sets (Shard 7)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands7` |Count |Total |\<none\>|PT1M |Yes|
|**Sets (Shard 8)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands8` |Count |Total |\<none\>|PT1M |Yes|
|**Sets (Shard 9)**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/metrics. |`setcommands9` |Count |Total |\<none\>|PT1M |Yes|
|**Total Operations**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed` |Count |Total |`ShardId`|PT1M |Yes|
|**Total Operations (Shard 0)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed0` |Count |Total |\<none\>|PT1M |Yes|
|**Total Operations (Shard 1)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed1` |Count |Total |\<none\>|PT1M |Yes|
|**Total Operations (Shard 2)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed2` |Count |Total |\<none\>|PT1M |Yes|
|**Total Operations (Shard 3)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed3` |Count |Total |\<none\>|PT1M |Yes|
|**Total Operations (Shard 4)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed4` |Count |Total |\<none\>|PT1M |Yes|
|**Total Operations (Shard 5)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed5` |Count |Total |\<none\>|PT1M |Yes|
|**Total Operations (Shard 6)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed6` |Count |Total |\<none\>|PT1M |Yes|
|**Total Operations (Shard 7)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed7` |Count |Total |\<none\>|PT1M |Yes|
|**Total Operations (Shard 8)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed8` |Count |Total |\<none\>|PT1M |Yes|
|**Total Operations (Shard 9)**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/metrics. |`totalcommandsprocessed9` |Count |Total |\<none\>|PT1M |Yes|
|**Total Keys**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys` |Count |Maximum |`ShardId`|PT1M |Yes|
|**Total Keys (Shard 0)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys0` |Count |Maximum |\<none\>|PT1M |Yes|
|**Total Keys (Shard 1)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys1` |Count |Maximum |\<none\>|PT1M |Yes|
|**Total Keys (Shard 2)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys2` |Count |Maximum |\<none\>|PT1M |Yes|
|**Total Keys (Shard 3)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys3` |Count |Maximum |\<none\>|PT1M |Yes|
|**Total Keys (Shard 4)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys4` |Count |Maximum |\<none\>|PT1M |Yes|
|**Total Keys (Shard 5)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys5` |Count |Maximum |\<none\>|PT1M |Yes|
|**Total Keys (Shard 6)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys6` |Count |Maximum |\<none\>|PT1M |Yes|
|**Total Keys (Shard 7)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys7` |Count |Maximum |\<none\>|PT1M |Yes|
|**Total Keys (Shard 8)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys8` |Count |Maximum |\<none\>|PT1M |Yes|
|**Total Keys (Shard 9)**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/metrics. |`totalkeys9` |Count |Maximum |\<none\>|PT1M |Yes|
|**Used Memory**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory` |Bytes |Maximum |`ShardId`|PT1M |Yes|
|**Used Memory (Shard 0)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory0` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory (Shard 1)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory1` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory (Shard 2)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory2` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory (Shard 3)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory3` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory (Shard 4)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory4` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory (Shard 5)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory5` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory (Shard 6)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory6` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory (Shard 7)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory7` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory (Shard 8)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory8` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory (Shard 9)**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/metrics. |`usedmemory9` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory Percentage**<p><p>The percentage of cache memory used for key/value pairs. For more details, see https://aka.ms/redis/metrics. |`usedmemorypercentage` |Percent |Maximum |`ShardId`|PT1M |Yes|
|**Used Memory RSS**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss` |Bytes |Maximum |`ShardId`|PT1M |Yes|
|**Used Memory RSS (Shard 0)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss0` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory RSS (Shard 1)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss1` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory RSS (Shard 2)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss2` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory RSS (Shard 3)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss3` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory RSS (Shard 4)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss4` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory RSS (Shard 5)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss5` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory RSS (Shard 6)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss6` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory RSS (Shard 7)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss7` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory RSS (Shard 8)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss8` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Used Memory RSS (Shard 9)**<p><p>The amount of cache memory used in MB, including fragmentation and metadata. For more details, see https://aka.ms/redis/metrics. |`usedmemoryRss9` |Bytes |Maximum |\<none\>|PT1M |Yes|