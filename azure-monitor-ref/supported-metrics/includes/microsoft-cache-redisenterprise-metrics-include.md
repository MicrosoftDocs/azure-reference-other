---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Cache/redisEnterprise, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Cache Hits**<br><br>The number of successful key lookups. For more details, see https://aka.ms/redis/enterprise/metrics. |`cachehits` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Cache Latency Microseconds (Preview)**<br><br>The latency to the cache in microseconds. For more details, see https://aka.ms/redis/enterprise/metrics. |`cacheLatency` |Count |Average |`InstanceId`|PT5M, PT1H |Yes|
|**Cache Misses**<br><br>The number of failed key lookups. For more details, see https://aka.ms/redis/enterprise/metrics. |`cachemisses` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Cache Read**<br><br>The amount of data read from the cache in Megabytes per second (MB/s). For more details, see https://aka.ms/redis/enterprise/metrics. |`cacheRead` |BytesPerSecond |Maximum |`InstanceId`|PT5M, PT1H |Yes|
|**Cache Write**<br><br>The amount of data written to the cache in Megabytes per second (MB/s). For more details, see https://aka.ms/redis/enterprise/metrics. |`cacheWrite` |BytesPerSecond |Maximum |`InstanceId`|PT5M, PT1H |Yes|
|**Connected Clients**<br><br>The number of client connections to the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`connectedclients` |Count |Maximum |`InstanceId`|PT5M, PT1H |Yes|
|**Evicted Keys**<br><br>The number of items evicted from the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`evictedkeys` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Expired Keys**<br><br>The number of items expired from the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`expiredkeys` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Geo Replication Healthy**<br><br>The health of geo replication in an Active Geo-Replication group. 0 represents Unhealthy and 1 represents Healthy. For more details, see https://aka.ms/redis/enterprise/metrics. |`geoReplicationHealthy` |Count |Maximum |\<none\>|PT5M, PT1H |Yes|
|**Gets**<br><br>The number of get operations from the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`getcommands` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Operations Per Second**<br><br>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`operationsPerSecond` |Count |Maximum |\<none\>|PT5M, PT1H |Yes|
|**CPU**<br><br>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/enterprise/metrics. |`percentProcessorTime` |Percent |Maximum |`InstanceId`|PT5M, PT1H |Yes|
|**Server Load**<br><br>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/enterprise/metrics. |`serverLoad` |Percent |Maximum |\<none\>|PT5M, PT1H |Yes|
|**Sets**<br><br>The number of set operations to the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`setcommands` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Total Operations**<br><br>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/enterprise/metrics. |`totalcommandsprocessed` |Count |Total |\<none\>|PT5M, PT1H |Yes|
|**Total Keys**<br><br>The total number of items in the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`totalkeys` |Count |Maximum |\<none\>|PT5M, PT1H |Yes|
|**Used Memory**<br><br>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/enterprise/metrics. |`usedmemory` |Bytes |Maximum |\<none\>|PT5M, PT1H |Yes|
|**Used Memory Percentage**<br><br>The percentage of cache memory used for key/value pairs. For more details, see https://aka.ms/redis/enterprise/metrics. |`usedmemorypercentage` |Percent |Maximum |\<none\>|PT5M, PT1H |Yes|