---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.HDInsight/clusters, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Categorized Gateway Requests**<p><p>Number of gateway requests by categories (1xx/2xx/3xx/4xx/5xx) |`CategorizedGatewayRequests` |Count |Count, Total |`HttpStatus`|PT1M, PT1H, P1D |Yes|
|**Gateway Requests**<p><p>Number of gateway requests |`GatewayRequests` |Count |Count, Total |`HttpStatus`|PT1M, PT1H, P1D |Yes|
|**REST proxy Consumer RequestThroughput**<p><p>Number of consumer requests to Kafka REST proxy |`KafkaRestProxy.ConsumerRequest.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**REST proxy Consumer Unsuccessful Requests**<p><p>Consumer request exceptions |`KafkaRestProxy.ConsumerRequestFail.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**REST proxy Consumer RequestLatency**<p><p>Message latency in a consumer request through Kafka REST proxy |`KafkaRestProxy.ConsumerRequestTime.p95` |Milliseconds |Average |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**REST proxy Consumer Request Backlog**<p><p>Consumer REST proxy queue length |`KafkaRestProxy.ConsumerRequestWaitingInQueueTime.p95` |Milliseconds |Average |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**REST proxy Producer MessageThroughput**<p><p>Number of producer messages through Kafka REST proxy |`KafkaRestProxy.MessagesIn.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**REST proxy Consumer MessageThroughput**<p><p>Number of consumer messages through Kafka REST proxy |`KafkaRestProxy.MessagesOut.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**REST proxy ConcurrentConnections**<p><p>Number of concurrent connections through Kafka REST proxy |`KafkaRestProxy.OpenConnections` |Count |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**REST proxy Producer RequestThroughput**<p><p>Number of producer requests to Kafka REST proxy |`KafkaRestProxy.ProducerRequest.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**REST proxy Producer Unsuccessful Requests**<p><p>Producer request exceptions |`KafkaRestProxy.ProducerRequestFail.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**REST proxy Producer RequestLatency**<p><p>Message latency in a producer request through Kafka REST proxy |`KafkaRestProxy.ProducerRequestTime.p95` |Milliseconds |Average |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**REST proxy Producer Request Backlog**<p><p>Producer REST proxy queue length |`KafkaRestProxy.ProducerRequestWaitingInQueueTime.p95` |Milliseconds |Average |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|**Number of Active Workers**<p><p>Number of Active Workers |`NumActiveWorkers` |Count |Average, Maximum, Minimum |`MetricName`|PT1M, PT1H, P1D |Yes|
|**Pending CPU**<p><p>Pending CPU Requests in YARN |`PendingCPU` |Count |Average, Maximum, Minimum |\<none\>|PT1M, PT1H, P1D |Yes|
|**Pending Memory**<p><p>Pending Memory Requests in YARN |`PendingMemory` |Count |Average, Maximum, Minimum |\<none\>|PT1M, PT1H, P1D |Yes|