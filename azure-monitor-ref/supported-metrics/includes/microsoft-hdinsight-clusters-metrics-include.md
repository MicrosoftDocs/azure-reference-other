---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.HDInsight/clusters, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Availability|**Categorized Gateway Requests**<br><br>Number of gateway requests by categories (1xx/2xx/3xx/4xx/5xx) |`CategorizedGatewayRequests` |Count |Count, Total |`HttpStatus`|PT1M, PT1H, P1D |Yes|
|Availability|**Gateway Requests**<br><br>Number of gateway requests |`GatewayRequests` |Count |Count, Total |`HttpStatus`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy Consumer RequestThroughput**<br><br>Number of consumer requests to Kafka REST proxy |`KafkaRestProxy.ConsumerRequest.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy Consumer Unsuccessful Requests**<br><br>Consumer request exceptions |`KafkaRestProxy.ConsumerRequestFail.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy Consumer RequestLatency**<br><br>Message latency in a consumer request through Kafka REST proxy |`KafkaRestProxy.ConsumerRequestTime.p95` |Milliseconds |Average |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy Consumer Request Backlog**<br><br>Consumer REST proxy queue length |`KafkaRestProxy.ConsumerRequestWaitingInQueueTime.p95` |Milliseconds |Average |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy Producer MessageThroughput**<br><br>Number of producer messages through Kafka REST proxy |`KafkaRestProxy.MessagesIn.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy Consumer MessageThroughput**<br><br>Number of consumer messages through Kafka REST proxy |`KafkaRestProxy.MessagesOut.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy ConcurrentConnections**<br><br>Number of concurrent connections through Kafka REST proxy |`KafkaRestProxy.OpenConnections` |Count |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy Producer RequestThroughput**<br><br>Number of producer requests to Kafka REST proxy |`KafkaRestProxy.ProducerRequest.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy Producer Unsuccessful Requests**<br><br>Producer request exceptions |`KafkaRestProxy.ProducerRequestFail.m1_delta` |CountPerSecond |Total |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy Producer RequestLatency**<br><br>Message latency in a producer request through Kafka REST proxy |`KafkaRestProxy.ProducerRequestTime.p95` |Milliseconds |Average |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**REST proxy Producer Request Backlog**<br><br>Producer REST proxy queue length |`KafkaRestProxy.ProducerRequestWaitingInQueueTime.p95` |Milliseconds |Average |`Machine`, `Topic`|PT1M, PT1H, P1D |Yes|
|Availability|**Number of Active Workers**<br><br>Number of Active Workers |`NumActiveWorkers` |Count |Average, Maximum, Minimum |`MetricName`|PT1M, PT1H, P1D |Yes|
|Availability|**Pending CPU**<br><br>Pending CPU Requests in YARN |`PendingCPU` |Count |Average, Maximum, Minimum |\<none\>|PT1M, PT1H, P1D |Yes|
|Availability|**Pending Memory**<br><br>Pending Memory Requests in YARN |`PendingMemory` |Count |Average, Maximum, Minimum |\<none\>|PT1M, PT1H, P1D |Yes|