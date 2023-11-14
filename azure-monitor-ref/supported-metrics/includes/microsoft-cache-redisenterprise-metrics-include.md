---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Cache/redisEnterprise, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Cache Hits**<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/enterprise/metrics. |`cachehits` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Cache Latency Microseconds (Preview)**<p><p>The latency to the cache in microseconds. For more details, see https://aka.ms/redis/enterprise/metrics. |`cacheLatency` |Count |Average |`InstanceId`|PT5M, PT1H |Yes|
|**Cache Misses**<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/enterprise/metrics. |`cachemisses` |Count |Total |`InstanceId`|PT5M, PT1H |Yes|
|**Cache Read**<p><p>The amount of data read from the cache in Megabytes per second (MB/s). For more details, see https://aka.ms/redis/enterprise/metrics. |`cacheRead` |BytesPerSecond |Maximum |`InstanceId`|PT5M, PT1H |Yes|
|**Cache Write**<p><p>The amount of data written to the cache in Megabytes per second (MB/s). For more details, see https://aka.ms/redis/enterprise/metrics. |`cacheWrite` |BytesPerSecond |Maximum |`InstanceId`|PT5M, PT1H |Yes|
|**Connected Clients**<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`connectedclients` |Count |Maximum |`InstanceId`|PT5M, PT1H |Yes|
|**Errors**<p><p>The number errors that occured on the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`errors` |Count |Maximum |`InstanceId`, `ErrorType`|PT5M, PT1H |Yes|
|**Evicted Keys**<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`evictedkeys` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Expired Keys**<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`expiredkeys` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Geo Replication Healthy**<p><p>The health of geo replication in an Active Geo-Replication group. 0 represents Unhealthy and 1 represents Healthy. For more details, see https://aka.ms/redis/enterprise/metrics. |`geoReplicationHealthy` |Count |Maximum |\<none\>|PT5M, PT1H |Yes|
|**Gets**<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`getcommands` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Operations Per Second**<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`operationsPerSecond` |Count |Maximum |\<none\>|PT5M, PT1H |Yes|
|**CPU**<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/enterprise/metrics. |`percentProcessorTime` |Percent |Maximum |`InstanceId`|PT5M, PT1H |Yes|
|**Server Load**<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/enterprise/metrics. |`serverLoad` |Percent |Maximum |\<none\>|PT5M, PT1H |Yes|
|**Sets**<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`setcommands` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Total Operations**<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/enterprise/metrics. |`totalcommandsprocessed` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Total Keys**<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`totalkeys` |Count |Maximum |\<none\>|PT5M, PT1H |Yes|
|**Used Memory**<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/enterprise/metrics. |`usedmemory` |Bytes |Maximum |\<none\>|PT5M, PT1H |Yes|
|**Used Memory Percentage**<p><p>The percentage of cache memory used for key/value pairs. For more details, see https://aka.ms/redis/enterprise/metrics. |`usedmemorypercentage` |Percent |Maximum |`InstanceId`|PT5M, PT1H |Yes|