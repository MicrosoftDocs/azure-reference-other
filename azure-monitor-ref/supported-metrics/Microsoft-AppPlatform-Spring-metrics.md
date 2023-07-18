---
title: Supported metrics - Microsoft.AppPlatform/Spring
description: Reference for Microsoft.AppPlatform/Spring metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.AppPlatform/Spring  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.AppPlatform/Spring resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|active-timer-count<p><p>Number of timers that are currently active |`active-timer-count` |Count |Average |Deployment, AppName, Pod |Yes|
|alloc-rate<p><p>Number of bytes allocated in the managed heap |`alloc-rate` |Bytes |Average |Deployment, AppName, Pod |Yes|
|App CPU Usage (Deprecated)<p><p>The recent CPU usage for the app. This metric is being deprecated. Please use "App CPU Usage" with metric id "PodCpuUsage". |`AppCpuUsage` |Percent |Average |Deployment, AppName, Pod |Yes|
|assembly-count<p><p>Number of Assemblies Loaded |`assembly-count` |Count |Average |Deployment, AppName, Pod |Yes|
|cpu-usage<p><p>% time the process has utilized the CPU |`cpu-usage` |Percent |Average |Deployment, AppName, Pod |Yes|
|current-requests<p><p>Total number of requests in processing in the lifetime of the process |`current-requests` |Count |Average |Deployment, AppName, Pod |Yes|
|exception-count<p><p>Number of Exceptions |`exception-count` |Count |Total |Deployment, AppName, Pod |Yes|
|failed-requests<p><p>Total number of failed requests in the lifetime of the process |`failed-requests` |Count |Average |Deployment, AppName, Pod |Yes|
|Max time of requests<p><p>The max time of requests |`GatewayHttpServerRequestsMilliSecondsMax` |Milliseconds |Maximum |Pod, httpStatusCode, outcome, httpMethod |Yes|
|Total time of requests<p><p>The total time of requests |`GatewayHttpServerRequestsMilliSecondsSum` |Milliseconds |Total |Pod, httpStatusCode, outcome, httpMethod |Yes|
|Request count<p><p>The number of requests |`GatewayHttpServerRequestsSecondsCount` |Count |Total |Pod, httpStatusCode, outcome, httpMethod |Yes|
|jvm.gc.live.data.size<p><p>Size of old generation memory pool after a full GC |`GatewayJvmGcLiveDataSizeBytes` |Bytes |Average |Pod |Yes|
|jvm.gc.max.data.size<p><p>Max size of old generation memory pool |`GatewayJvmGcMaxDataSizeBytes` |Bytes |Maximum |Pod |Yes|
|jvm.gc.memory.allocated<p><p>Incremented for an increase in the size of the young generation memory pool after one GC to before the next |`GatewayJvmGcMemoryAllocatedBytesTotal` |Bytes |Maximum |Pod |Yes|
|jvm.gc.memory.promoted<p><p>Count of positive increases in the size of the old generation memory pool before GC to after GC |`GatewayJvmGcMemoryPromotedBytesTotal` |Bytes |Maximum |Pod |Yes|
|jvm.gc.pause.total.count<p><p>GC Pause Count |`GatewayJvmGcPauseSecondsCount` |Count |Total |Pod |Yes|
|jvm.gc.pause.max.time<p><p>GC Pause Max Time |`GatewayJvmGcPauseSecondsMax` |Seconds |Maximum |Pod |Yes|
|jvm.gc.pause.total.time<p><p>GC Pause Total Time |`GatewayJvmGcPauseSecondsSum` |Seconds |Total |Pod |Yes|
|jvm.memory.committed<p><p>Memory assigned to JVM in bytes |`GatewayJvmMemoryCommittedBytes` |Bytes |Average |Pod |Yes|
|jvm.memory.used<p><p>Memory Used in bytes |`GatewayJvmMemoryUsedBytes` |Bytes |Average |Pod |Yes|
|process.cpu.usage<p><p>The recent CPU usage for the JVM process |`GatewayProcessCpuUsage` |Percent |Average |Pod |Yes|
|Throttled requests count<p><p>The count of the throttled requests |`GatewayRatelimitThrottledCount` |Count |Total |Pod |Yes|
|system.cpu.usage<p><p>The recent CPU usage for the whole system |`GatewaySystemCpuUsage` |Percent |Average |Pod |Yes|
|gc-heap-size<p><p>Total heap size reported by the GC (MB) |`gc-heap-size` |Count |Average |Deployment, AppName, Pod |Yes|
|gen-0-gc-count<p><p>Number of Gen 0 GCs |`gen-0-gc-count` |Count |Average |Deployment, AppName, Pod |Yes|
|gen-0-size<p><p>Gen 0 Heap Size |`gen-0-size` |Bytes |Average |Deployment, AppName, Pod |Yes|
|gen-1-gc-count<p><p>Number of Gen 1 GCs |`gen-1-gc-count` |Count |Average |Deployment, AppName, Pod |Yes|
|gen-1-size<p><p>Gen 1 Heap Size |`gen-1-size` |Bytes |Average |Deployment, AppName, Pod |Yes|
|gen-2-gc-count<p><p>Number of Gen 2 GCs |`gen-2-gc-count` |Count |Average |Deployment, AppName, Pod |Yes|
|gen-2-size<p><p>Gen 2 Heap Size |`gen-2-size` |Bytes |Average |Deployment, AppName, Pod |Yes|
|Bytes Received<p><p>Count of bytes received by Azure Spring Apps from the clients |`IngressBytesReceived` |Bytes |Average |Hostname, HttpStatus |Yes|
|Throughput In (bytes/s)<p><p>Bytes received per second by Azure Spring Apps from the clients |`IngressBytesReceivedRate` |BytesPerSecond |Average |Hostname, HttpStatus |Yes|
|Bytes Sent<p><p>Count of bytes sent by Azure Spring Apps to the clients |`IngressBytesSent` |Bytes |Average |Hostname, HttpStatus |Yes|
|Throughput Out (bytes/s)<p><p>Bytes sent per second by Azure Spring Apps to the clients |`IngressBytesSentRate` |BytesPerSecond |Average |Hostname, HttpStatus |Yes|
|Failed Requests<p><p>Count of failed requests by Azure Spring Apps from the clients |`IngressFailedRequests` |Count |Average |Hostname, HttpStatus |Yes|
|Requests<p><p>Count of requests by Azure Spring Apps from the clients |`IngressRequests` |Count |Average |Hostname, HttpStatus |Yes|
|Response Status<p><p>HTTP response status returned by Azure Spring Apps. The response status code distribution can be further categorized to show responses in 2xx, 3xx, 4xx, and 5xx categories |`IngressResponseStatus` |Count |Average |Hostname, HttpStatus |Yes|
|Response Time<p><p>Http response time return by Azure Spring Apps |`IngressResponseTime` |Seconds |Average |Hostname, HttpStatus |Yes|
|jvm.gc.live.data.size<p><p>Size of old generation memory pool after a full GC |`jvm.gc.live.data.size` |Bytes |Average |Deployment, AppName, Pod |Yes|
|jvm.gc.max.data.size<p><p>Max size of old generation memory pool |`jvm.gc.max.data.size` |Bytes |Average |Deployment, AppName, Pod |Yes|
|jvm.gc.memory.allocated<p><p>Incremented for an increase in the size of the young generation memory pool after one GC to before the next |`jvm.gc.memory.allocated` |Bytes |Maximum |Deployment, AppName, Pod |Yes|
|jvm.gc.memory.promoted<p><p>Count of positive increases in the size of the old generation memory pool before GC to after GC |`jvm.gc.memory.promoted` |Bytes |Maximum |Deployment, AppName, Pod |Yes|
|jvm.gc.pause.total.count<p><p>GC Pause Count |`jvm.gc.pause.total.count` |Count |Total |Deployment, AppName, Pod |Yes|
|jvm.gc.pause.total.time<p><p>GC Pause Total Time |`jvm.gc.pause.total.time` |Milliseconds |Total |Deployment, AppName, Pod |Yes|
|jvm.memory.committed<p><p>Memory assigned to JVM in bytes |`jvm.memory.committed` |Bytes |Average |Deployment, AppName, Pod |Yes|
|jvm.memory.max<p><p>The maximum amount of memory in bytes that can be used for memory management |`jvm.memory.max` |Bytes |Maximum |Deployment, AppName, Pod |Yes|
|jvm.memory.used<p><p>App Memory Used in bytes |`jvm.memory.used` |Bytes |Average |Deployment, AppName, Pod |Yes|
|loh-size<p><p>LOH Heap Size |`loh-size` |Bytes |Average |Deployment, AppName, Pod |Yes|
|monitor-lock-contention-count<p><p>Number of times there were contention when trying to take the monitor lock |`monitor-lock-contention-count` |Count |Average |Deployment, AppName, Pod |Yes|
|App CPU Usage<p><p>The recent CPU usage for the app |`PodCpuUsage` |Percent |Average |Deployment, AppName, Pod |Yes|
|App Memory Usage<p><p>The recent Memory usage for the app |`PodMemoryUsage` |Percent |Average |Deployment, AppName, Pod |Yes|
|App Network In<p><p>Cumulative count of bytes received in the app |`PodNetworkIn` |Bytes |Average |Deployment, AppName, Pod |Yes|
|App Network Out<p><p>Cumulative count of bytes sent from the app |`PodNetworkOut` |Bytes |Average |Deployment, AppName, Pod |Yes|
|process.cpu.usage<p><p>The recent CPU usage for the JVM process |`process.cpu.usage` |Percent |Average |Deployment, AppName, Pod |Yes|
|Requests<p><p>Requests processed |`Requests` |Count |Total |containerAppName, podName, statusCodeCategory, statusCode |Yes|
|requests-rate<p><p>Request rate |`requests-per-second` |Count |Average |Deployment, AppName, Pod |Yes|
|Restart Count<p><p>Restart count of Spring App |`RestartCount` |Count |Maximum |containerAppName, podName |Yes|
|Network In Bytes<p><p>Network received bytes |`RxBytes` |Bytes |Total |containerAppName, podName |Yes|
|system.cpu.usage<p><p>The recent CPU usage for the whole system |`system.cpu.usage` |Percent |Average |Deployment, AppName, Pod |Yes|
|threadpool-completed-items-count<p><p>ThreadPool Completed Work Items Count |`threadpool-completed-items-count` |Count |Average |Deployment, AppName, Pod |Yes|
|threadpool-queue-length<p><p>ThreadPool Work Items Queue Length |`threadpool-queue-length` |Count |Average |Deployment, AppName, Pod |Yes|
|threadpool-thread-count<p><p>Number of ThreadPool Threads |`threadpool-thread-count` |Count |Average |Deployment, AppName, Pod |Yes|
|time-in-gc<p><p>% time in GC since the last GC |`time-in-gc` |Percent |Average |Deployment, AppName, Pod |Yes|
|tomcat.global.error<p><p>Tomcat Global Error |`tomcat.global.error` |Count |Total |Deployment, AppName, Pod |Yes|
|tomcat.global.received<p><p>Tomcat Total Received Bytes |`tomcat.global.received` |Bytes |Total |Deployment, AppName, Pod |Yes|
|tomcat.global.request.avg.time<p><p>Tomcat Request Average Time |`tomcat.global.request.avg.time` |Milliseconds |Average |Deployment, AppName, Pod |Yes|
|tomcat.global.request.max<p><p>Tomcat Request Max Time |`tomcat.global.request.max` |Milliseconds |Maximum |Deployment, AppName, Pod |Yes|
|tomcat.global.request.total.count<p><p>Tomcat Request Total Count |`tomcat.global.request.total.count` |Count |Total |Deployment, AppName, Pod |Yes|
|tomcat.global.request.total.time<p><p>Tomcat Request Total Time |`tomcat.global.request.total.time` |Milliseconds |Total |Deployment, AppName, Pod |Yes|
|tomcat.global.sent<p><p>Tomcat Total Sent Bytes |`tomcat.global.sent` |Bytes |Total |Deployment, AppName, Pod |Yes|
|tomcat.sessions.active.current<p><p>Tomcat Session Active Count |`tomcat.sessions.active.current` |Count |Total |Deployment, AppName, Pod |Yes|
|tomcat.sessions.active.max<p><p>Tomcat Session Max Active Count |`tomcat.sessions.active.max` |Count |Total |Deployment, AppName, Pod |Yes|
|tomcat.sessions.alive.max<p><p>Tomcat Session Max Alive Time |`tomcat.sessions.alive.max` |Milliseconds |Maximum |Deployment, AppName, Pod |Yes|
|tomcat.sessions.created<p><p>Tomcat Session Created Count |`tomcat.sessions.created` |Count |Total |Deployment, AppName, Pod |Yes|
|tomcat.sessions.expired<p><p>Tomcat Session Expired Count |`tomcat.sessions.expired` |Count |Total |Deployment, AppName, Pod |Yes|
|tomcat.sessions.rejected<p><p>Tomcat Session Rejected Count |`tomcat.sessions.rejected` |Count |Total |Deployment, AppName, Pod |Yes|
|tomcat.threads.config.max<p><p>Tomcat Config Max Thread Count |`tomcat.threads.config.max` |Count |Total |Deployment, AppName, Pod |Yes|
|tomcat.threads.current<p><p>Tomcat Current Thread Count |`tomcat.threads.current` |Count |Total |Deployment, AppName, Pod |Yes|
|total-requests<p><p>Total number of requests in the lifetime of the process |`total-requests` |Count |Average |Deployment, AppName, Pod |Yes|
|Network Out Bytes<p><p>Network transmitted bytes |`TxBytes` |Bytes |Total |containerAppName, podName |Yes|
|CPU Usage<p><p>CPU consumed by Spring App, in nano cores. 1,000,000,000 nano cores = 1 core |`UsageNanoCores` |NanoCores |Average |containerAppName, podName |Yes|
|working-set<p><p>Amount of working set used by the process (MB) |`working-set` |Count |Average |Deployment, AppName, Pod |Yes|
|Memory Working Set Bytes<p><p>Spring App working set memory used in bytes. |`WorkingSetBytes` |Bytes |Average |containerAppName, podName |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->