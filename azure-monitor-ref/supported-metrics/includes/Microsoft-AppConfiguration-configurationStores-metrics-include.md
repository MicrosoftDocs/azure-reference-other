---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.AppConfiguration/configurationStores, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|DailyStorageUsage<p><p>Total storage usage of the store in percentage. Updated at minimum every 24 hours. |`DailyStorageUsage` |Percent |Minimum, Maximum |No Dimensions|PT1M |Yes|
|HttpIncomingRequestCount<p><p>Total number of incoming http requests. |`HttpIncomingRequestCount` |Count |Total |StatusCode, Authentication, Endpoint|PT1M |Yes|
|HttpIncomingRequestDuration<p><p>Latency on an http request. |`HttpIncomingRequestDuration` |Milliseconds |Average |StatusCode, Authentication, Endpoint|PT1M |Yes|
|ReplicationLatency<p><p>Latency of replication. Average time it takes for a replica to be consistent with current state. |`ReplicationLatency` |Milliseconds |Average |Endpoint|PT1M |Yes|
|ThrottledHttpRequestCount<p><p>Throttled http requests. |`ThrottledHttpRequestCount` |Count |Total |Endpoint|PT1M |Yes|