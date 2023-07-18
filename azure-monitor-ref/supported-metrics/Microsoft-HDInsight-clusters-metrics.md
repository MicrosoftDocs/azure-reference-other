---
title: Supported metrics - Microsoft.HDInsight/clusters
description: Reference for Microsoft.HDInsight/clusters metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.HDInsight/clusters  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.HDInsight/clusters resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Categorized Gateway Requests<p><p>Number of gateway requests by categories (1xx/2xx/3xx/4xx/5xx) |`CategorizedGatewayRequests` |Count |Total |HttpStatus |Yes|
|Gateway Requests<p><p>Number of gateway requests |`GatewayRequests` |Count |Total |HttpStatus |Yes|
|REST proxy Consumer RequestThroughput<p><p>Number of consumer requests to Kafka REST proxy |`KafkaRestProxy.ConsumerRequest.m1_delta` |CountPerSecond |Total |Machine, Topic |Yes|
|REST proxy Consumer Unsuccessful Requests<p><p>Consumer request exceptions |`KafkaRestProxy.ConsumerRequestFail.m1_delta` |CountPerSecond |Total |Machine, Topic |Yes|
|REST proxy Consumer RequestLatency<p><p>Message latency in a consumer request through Kafka REST proxy |`KafkaRestProxy.ConsumerRequestTime.p95` |Milliseconds |Average |Machine, Topic |Yes|
|REST proxy Consumer Request Backlog<p><p>Consumer REST proxy queue length |`KafkaRestProxy.ConsumerRequestWaitingInQueueTime.p95` |Milliseconds |Average |Machine, Topic |Yes|
|REST proxy Producer MessageThroughput<p><p>Number of producer messages through Kafka REST proxy |`KafkaRestProxy.MessagesIn.m1_delta` |CountPerSecond |Total |Machine, Topic |Yes|
|REST proxy Consumer MessageThroughput<p><p>Number of consumer messages through Kafka REST proxy |`KafkaRestProxy.MessagesOut.m1_delta` |CountPerSecond |Total |Machine, Topic |Yes|
|REST proxy ConcurrentConnections<p><p>Number of concurrent connections through Kafka REST proxy |`KafkaRestProxy.OpenConnections` |Count |Total |Machine, Topic |Yes|
|REST proxy Producer RequestThroughput<p><p>Number of producer requests to Kafka REST proxy |`KafkaRestProxy.ProducerRequest.m1_delta` |CountPerSecond |Total |Machine, Topic |Yes|
|REST proxy Producer Unsuccessful Requests<p><p>Producer request exceptions |`KafkaRestProxy.ProducerRequestFail.m1_delta` |CountPerSecond |Total |Machine, Topic |Yes|
|REST proxy Producer RequestLatency<p><p>Message latency in a producer request through Kafka REST proxy |`KafkaRestProxy.ProducerRequestTime.p95` |Milliseconds |Average |Machine, Topic |Yes|
|REST proxy Producer Request Backlog<p><p>Producer REST proxy queue length |`KafkaRestProxy.ProducerRequestWaitingInQueueTime.p95` |Milliseconds |Average |Machine, Topic |Yes|
|Number of Active Workers<p><p>Number of Active Workers |`NumActiveWorkers` |Count |Maximum |MetricName |Yes|
|Pending CPU<p><p>Pending CPU Requests in YARN |`PendingCPU` |Count |Maximum |No Dimensions |Yes|
|Pending Memory<p><p>Pending Memory Requests in YARN |`PendingMemory` |Count |Maximum |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->