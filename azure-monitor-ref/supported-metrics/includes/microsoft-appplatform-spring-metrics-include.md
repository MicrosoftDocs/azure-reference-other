---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.AppPlatform/Spring, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Performance (.NET)|**active-timer-count**<p><p>Number of timers that are currently active |`active-timer-count` |Count |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**alloc-rate**<p><p>Number of bytes allocated in the managed heap |`alloc-rate` |Bytes |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Common|**App CPU Usage (Deprecated)**<p><p>The recent CPU usage for the app. This metric is being deprecated. Please use "App CPU Usage" with metric id "PodCpuUsage". |`AppCpuUsage` |Percent |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**assembly-count**<p><p>Number of Assemblies Loaded |`assembly-count` |Count |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**cpu-usage**<p><p>% time the process has utilized the CPU |`cpu-usage` |Percent |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (.NET)|**current-requests**<p><p>Total number of requests in processing in the lifetime of the process |`current-requests` |Count |Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**exception-count**<p><p>Number of Exceptions |`exception-count` |Count |Total, Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (.NET)|**failed-requests**<p><p>Total number of failed requests in the lifetime of the process |`failed-requests` |Count |Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Gateway|**Max time of requests**<p><p>The max time of requests |`GatewayHttpServerRequestsMilliSecondsMax` |Milliseconds |Maximum, Average |`Pod`, `httpStatusCode`, `outcome`, `httpMethod`|PT1M |Yes|
|Gateway|**Total time of requests**<p><p>The total time of requests |`GatewayHttpServerRequestsMilliSecondsSum` |Milliseconds |Maximum, Minimum, Average |`Pod`, `httpStatusCode`, `outcome`, `httpMethod`|PT1M |Yes|
|Gateway|**Request count**<p><p>The number of requests |`GatewayHttpServerRequestsSecondsCount` |Count |Total, Average |`Pod`, `httpStatusCode`, `outcome`, `httpMethod`|PT1M |Yes|
|Gateway|**jvm.gc.live.data.size**<p><p>Size of old generation memory pool after a full GC |`GatewayJvmGcLiveDataSizeBytes` |Bytes |Maximum, Average |`Pod`|PT1M |Yes|
|Gateway|**jvm.gc.max.data.size**<p><p>Max size of old generation memory pool |`GatewayJvmGcMaxDataSizeBytes` |Bytes |Maximum, Average |`Pod`|PT1M |Yes|
|Gateway|**jvm.gc.memory.allocated**<p><p>Incremented for an increase in the size of the young generation memory pool after one GC to before the next |`GatewayJvmGcMemoryAllocatedBytesTotal` |Bytes |Maximum, Average |`Pod`|PT1M |Yes|
|Gateway|**jvm.gc.memory.promoted**<p><p>Count of positive increases in the size of the old generation memory pool before GC to after GC |`GatewayJvmGcMemoryPromotedBytesTotal` |Bytes |Maximum, Average |`Pod`|PT1M |Yes|
|Gateway|**jvm.gc.pause.total.count**<p><p>GC Pause Count |`GatewayJvmGcPauseSecondsCount` |Count |Total, Average |`Pod`|PT1M |Yes|
|Gateway|**jvm.gc.pause.max.time**<p><p>GC Pause Max Time |`GatewayJvmGcPauseSecondsMax` |Seconds |Maximum, Average |`Pod`|PT1M |Yes|
|Gateway|**jvm.gc.pause.total.time**<p><p>GC Pause Total Time |`GatewayJvmGcPauseSecondsSum` |Seconds |Total, Average |`Pod`|PT1M |Yes|
|Gateway|**jvm.memory.committed**<p><p>Memory assigned to JVM in bytes |`GatewayJvmMemoryCommittedBytes` |Bytes |Maximum, Minimum, Average |`Pod`|PT1M |Yes|
|Gateway|**jvm.memory.used**<p><p>Memory Used in bytes |`GatewayJvmMemoryUsedBytes` |Bytes |Maximum, Minimum, Average |`Pod`|PT1M |Yes|
|Gateway|**process.cpu.usage**<p><p>The recent CPU usage for the JVM process |`GatewayProcessCpuUsage` |Percent |Maximum, Minimum, Average |`Pod`|PT1M |Yes|
|Gateway|**Throttled requests count**<p><p>The count of the throttled requests |`GatewayRatelimitThrottledCount` |Count |Total, Average |`Pod`|PT1M |Yes|
|Gateway|**system.cpu.usage**<p><p>The recent CPU usage for the whole system |`GatewaySystemCpuUsage` |Percent |Maximum, Minimum, Average |`Pod`|PT1M |Yes|
|Performance (.NET)|**gc-heap-size**<p><p>Total heap size reported by the GC (MB) |`gc-heap-size` |Count |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**gen-0-gc-count**<p><p>Number of Gen 0 GCs |`gen-0-gc-count` |Count |Total, Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**gen-0-size**<p><p>Gen 0 Heap Size |`gen-0-size` |Bytes |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**gen-1-gc-count**<p><p>Number of Gen 1 GCs |`gen-1-gc-count` |Count |Total, Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**gen-1-size**<p><p>Gen 1 Heap Size |`gen-1-size` |Bytes |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**gen-2-gc-count**<p><p>Number of Gen 2 GCs |`gen-2-gc-count` |Count |Total, Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**gen-2-size**<p><p>Gen 2 Heap Size |`gen-2-size` |Bytes |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Ingress|**Bytes Received**<p><p>Count of bytes received by Azure Spring Apps from the clients |`IngressBytesReceived` |Bytes |Maximum, Minimum, Average |`Hostname`, `HttpStatus`|PT1M |Yes|
|Ingress|**Throughput In (bytes/s)**<p><p>Bytes received per second by Azure Spring Apps from the clients |`IngressBytesReceivedRate` |BytesPerSecond |Maximum, Minimum, Average |`Hostname`, `HttpStatus`|PT1M |Yes|
|Ingress|**Bytes Sent**<p><p>Count of bytes sent by Azure Spring Apps to the clients |`IngressBytesSent` |Bytes |Maximum, Minimum, Average |`Hostname`, `HttpStatus`|PT1M |Yes|
|Ingress|**Throughput Out (bytes/s)**<p><p>Bytes sent per second by Azure Spring Apps to the clients |`IngressBytesSentRate` |BytesPerSecond |Maximum, Minimum, Average |`Hostname`, `HttpStatus`|PT1M |Yes|
|Ingress|**Failed Requests**<p><p>Count of failed requests by Azure Spring Apps from the clients |`IngressFailedRequests` |Count |Maximum, Minimum, Average |`Hostname`, `HttpStatus`|PT1M |Yes|
|Ingress|**Requests**<p><p>Count of requests by Azure Spring Apps from the clients |`IngressRequests` |Count |Maximum, Minimum, Average |`Hostname`, `HttpStatus`|PT1M |Yes|
|Ingress|**Response Status**<p><p>HTTP response status returned by Azure Spring Apps. The response status code distribution can be further categorized to show responses in 2xx, 3xx, 4xx, and 5xx categories |`IngressResponseStatus` |Count |Maximum, Minimum, Average |`Hostname`, `HttpStatus`|PT1M |Yes|
|Ingress|**Response Time**<p><p>Http response time return by Azure Spring Apps |`IngressResponseTime` |Seconds |Maximum, Minimum, Average |`Hostname`, `HttpStatus`|PT1M |Yes|
|Performance (Java)|**jvm.gc.live.data.size**<p><p>Size of old generation memory pool after a full GC |`jvm.gc.live.data.size` |Bytes |Maximum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (Java)|**jvm.gc.max.data.size**<p><p>Max size of old generation memory pool |`jvm.gc.max.data.size` |Bytes |Maximum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (Java)|**jvm.gc.memory.allocated**<p><p>Incremented for an increase in the size of the young generation memory pool after one GC to before the next |`jvm.gc.memory.allocated` |Bytes |Maximum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (Java)|**jvm.gc.memory.promoted**<p><p>Count of positive increases in the size of the old generation memory pool before GC to after GC |`jvm.gc.memory.promoted` |Bytes |Maximum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (Java)|**jvm.gc.pause.total.count**<p><p>GC Pause Count |`jvm.gc.pause.total.count` |Count |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (Java)|**jvm.gc.pause.total.time**<p><p>GC Pause Total Time |`jvm.gc.pause.total.time` |Milliseconds |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (Java)|**jvm.memory.committed**<p><p>Memory assigned to JVM in bytes |`jvm.memory.committed` |Bytes |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (Java)|**jvm.memory.max**<p><p>The maximum amount of memory in bytes that can be used for memory management |`jvm.memory.max` |Bytes |Maximum |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (Java)|**jvm.memory.used**<p><p>App Memory Used in bytes |`jvm.memory.used` |Bytes |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**loh-size**<p><p>LOH Heap Size |`loh-size` |Bytes |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**monitor-lock-contention-count**<p><p>Number of times there were contention when trying to take the monitor lock |`monitor-lock-contention-count` |Count |Total, Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Common|**App CPU Usage**<p><p>The recent CPU usage for the app |`PodCpuUsage` |Percent |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Common|**App Memory Usage**<p><p>The recent Memory usage for the app |`PodMemoryUsage` |Percent |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Common|**App Network In**<p><p>Cumulative count of bytes received in the app |`PodNetworkIn` |Bytes |Total, Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Common|**App Network Out**<p><p>Cumulative count of bytes sent from the app |`PodNetworkOut` |Bytes |Total, Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (Java)|**process.cpu.usage**<p><p>The recent CPU usage for the JVM process |`process.cpu.usage` |Percent |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Core|**Requests**<p><p>Requests processed |`Requests` |Count |Total, Maximum, Minimum, Average |`containerAppName`, `podName`, `statusCodeCategory`, `statusCode`|PT1M |Yes|
|Request (.NET)|**requests-rate**<p><p>Request rate |`requests-per-second` |Count |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Core|**Restart Count**<p><p>Restart count of Spring App |`RestartCount` |Count |Total, Maximum, Minimum, Average |`containerAppName`, `podName`|PT1M |Yes|
|Core|**Network In Bytes**<p><p>Network received bytes |`RxBytes` |Bytes |Total, Maximum, Minimum, Average |`containerAppName`, `podName`|PT1M |Yes|
|Performance (Java)|**system.cpu.usage**<p><p>The recent CPU usage for the whole system |`system.cpu.usage` |Percent |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**threadpool-completed-items-count**<p><p>ThreadPool Completed Work Items Count |`threadpool-completed-items-count` |Count |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**threadpool-queue-length**<p><p>ThreadPool Work Items Queue Length |`threadpool-queue-length` |Count |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**threadpool-thread-count**<p><p>Number of ThreadPool Threads |`threadpool-thread-count` |Count |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Performance (.NET)|**time-in-gc**<p><p>% time in GC since the last GC |`time-in-gc` |Percent |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Error (Java)|**tomcat.global.error**<p><p>Tomcat Global Error |`tomcat.global.error` |Count |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (Java)|**tomcat.global.received**<p><p>Tomcat Total Received Bytes |`tomcat.global.received` |Bytes |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (Java)|**tomcat.global.request.avg.time**<p><p>Tomcat Request Average Time |`tomcat.global.request.avg.time` |Milliseconds |Maximum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (Java)|**tomcat.global.request.max**<p><p>Tomcat Request Max Time |`tomcat.global.request.max` |Milliseconds |Maximum |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (Java)|**tomcat.global.request.total.count**<p><p>Tomcat Request Total Count |`tomcat.global.request.total.count` |Count |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (Java)|**tomcat.global.request.total.time**<p><p>Tomcat Request Total Time |`tomcat.global.request.total.time` |Milliseconds |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (Java)|**tomcat.global.sent**<p><p>Tomcat Total Sent Bytes |`tomcat.global.sent` |Bytes |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Session (Java)|**tomcat.sessions.active.current**<p><p>Tomcat Session Active Count |`tomcat.sessions.active.current` |Count |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Session (Java)|**tomcat.sessions.active.max**<p><p>Tomcat Session Max Active Count |`tomcat.sessions.active.max` |Count |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Session (Java)|**tomcat.sessions.alive.max**<p><p>Tomcat Session Max Alive Time |`tomcat.sessions.alive.max` |Milliseconds |Maximum |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Session (Java)|**tomcat.sessions.created**<p><p>Tomcat Session Created Count |`tomcat.sessions.created` |Count |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Session (Java)|**tomcat.sessions.expired**<p><p>Tomcat Session Expired Count |`tomcat.sessions.expired` |Count |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Session (Java)|**tomcat.sessions.rejected**<p><p>Tomcat Session Rejected Count |`tomcat.sessions.rejected` |Count |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (Java)|**tomcat.threads.config.max**<p><p>Tomcat Config Max Thread Count |`tomcat.threads.config.max` |Count |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (Java)|**tomcat.threads.current**<p><p>Tomcat Current Thread Count |`tomcat.threads.current` |Count |Total, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Request (.NET)|**total-requests**<p><p>Total number of requests in the lifetime of the process |`total-requests` |Count |Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Core|**Network Out Bytes**<p><p>Network transmitted bytes |`TxBytes` |Bytes |Total, Maximum, Minimum, Average |`containerAppName`, `podName`|PT1M |Yes|
|Core|**CPU Usage**<p><p>CPU consumed by Spring App, in nano cores. 1,000,000,000 nano cores = 1 core |`UsageNanoCores` |NanoCores |Total, Maximum, Minimum, Average |`containerAppName`, `podName`|PT1M |Yes|
|Performance (.NET)|**working-set**<p><p>Amount of working set used by the process (MB) |`working-set` |Count |Maximum, Minimum, Average |`Deployment`, `AppName`, `Pod`|PT1M |Yes|
|Core|**Memory Working Set Bytes**<p><p>Spring App working set memory used in bytes. |`WorkingSetBytes` |Bytes |Total, Maximum, Minimum, Average |`containerAppName`, `podName`|PT1M |Yes|