---
title: Supported metrics - Microsoft.Cache/redisEnterprise
description: Reference for Microsoft.Cache/redisEnterprise metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Cache/redisEnterprise  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Cache/redisEnterprise resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Cache Hits<p><p>The number of successful key lookups. For more details, see https://aka.ms/redis/enterprise/metrics. |`cachehits` |Count |Total |No Dimensions |Yes|
|Cache Latency Microseconds (Preview)<p><p>The latency to the cache in microseconds. For more details, see https://aka.ms/redis/enterprise/metrics. |`cacheLatency` |Count |Average |InstanceId |Yes|
|Cache Misses<p><p>The number of failed key lookups. For more details, see https://aka.ms/redis/enterprise/metrics. |`cachemisses` |Count |Total |InstanceId |Yes|
|Cache Read<p><p>The amount of data read from the cache in Megabytes per second (MB/s). For more details, see https://aka.ms/redis/enterprise/metrics. |`cacheRead` |BytesPerSecond |Maximum |InstanceId |Yes|
|Cache Write<p><p>The amount of data written to the cache in Megabytes per second (MB/s). For more details, see https://aka.ms/redis/enterprise/metrics. |`cacheWrite` |BytesPerSecond |Maximum |InstanceId |Yes|
|Connected Clients<p><p>The number of client connections to the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`connectedclients` |Count |Maximum |InstanceId |Yes|
|Errors<p><p>The number errors that occured on the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`errors` |Count |Maximum |InstanceId, ErrorType |Yes|
|Evicted Keys<p><p>The number of items evicted from the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`evictedkeys` |Count |Total |No Dimensions |Yes|
|Expired Keys<p><p>The number of items expired from the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`expiredkeys` |Count |Total |No Dimensions |Yes|
|Geo Replication Healthy<p><p>The health of geo replication in an Active Geo-Replication group. 0 represents Unhealthy and 1 represents Healthy. For more details, see https://aka.ms/redis/enterprise/metrics. |`geoReplicationHealthy` |Count |Maximum |No Dimensions |Yes|
|Gets<p><p>The number of get operations from the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`getcommands` |Count |Total |No Dimensions |Yes|
|Operations Per Second<p><p>The number of instantaneous operations per second executed on the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`operationsPerSecond` |Count |Maximum |No Dimensions |Yes|
|CPU<p><p>The CPU utilization of the Azure Redis Cache server as a percentage. For more details, see https://aka.ms/redis/enterprise/metrics. |`percentProcessorTime` |Percent |Maximum |InstanceId |Yes|
|Server Load<p><p>The percentage of cycles in which the Redis server is busy processing and not waiting idle for messages. For more details, see https://aka.ms/redis/enterprise/metrics. |`serverLoad` |Percent |Maximum |No Dimensions |Yes|
|Sets<p><p>The number of set operations to the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`setcommands` |Count |Total |No Dimensions |Yes|
|Total Operations<p><p>The total number of commands processed by the cache server. For more details, see https://aka.ms/redis/enterprise/metrics. |`totalcommandsprocessed` |Count |Total |No Dimensions |Yes|
|Total Keys<p><p>The total number of items in the cache. For more details, see https://aka.ms/redis/enterprise/metrics. |`totalkeys` |Count |Maximum |No Dimensions |Yes|
|Used Memory<p><p>The amount of cache memory used for key/value pairs in the cache in MB. For more details, see https://aka.ms/redis/enterprise/metrics. |`usedmemory` |Bytes |Maximum |No Dimensions |Yes|
|Used Memory Percentage<p><p>The percentage of cache memory used for key/value pairs. For more details, see https://aka.ms/redis/enterprise/metrics. |`usedmemorypercentage` |Percent |Maximum |InstanceId |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->