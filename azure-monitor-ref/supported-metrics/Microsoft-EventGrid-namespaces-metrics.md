---
title: Supported metrics - Microsoft.EventGrid/namespaces
description: Reference for Microsoft.EventGrid/namespaces metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/13/2023
---
# Supported metrics for Microsoft.EventGrid/namespaces  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.EventGrid/namespaces resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Acknowledge Operations Latency<p><p>The observed latency in milliseconds for acknowledge events operation. |`AcknowledgeLatencyInMilliseconds` |Milliseconds |Total |Topic, EventSubscriptionName |No|
|Failed Acknowledged Events<p><p>The number of events for which acknowledgements from clients failed. |`FailedAcknowledgedEvents` |Count |Total |Topic, EventSubscriptionName, Error, ErrorType |No|
|Failed Publish Events<p><p>The number of events that weren't accepted by Event Grid. This count excludes events that were published but failed to reach Event Grid due to a network issue, for example. |`FailedPublishedEvents` |Count |Total |Topic, Error, ErrorType |No|
|Failed Received Events<p><p>The number of events that were requested by clients but weren't delivered successfully by Event Grid. |`FailedReceivedEvents` |Count |Total |Topic, EventSubscriptionName, Error, ErrorType |No|
|Failed Released Events<p><p>The number of events for which release failed. |`FailedReleasedEvents` |Count |Total |Topic, EventSubscriptionName, Error, ErrorType |No|
|MQTT: Connections<p><p>The number of active connections in the namespace. |`Mqtt.Connections` |Count |Total |Protocol |Yes|
|MQTT: Failed Published Messages<p><p>The number of MQTT messages that failed to be published into the namespace. |`Mqtt.FailedPublishedMessages` |Count |Total |QoS, Protocol, Error |Yes|
|MQTT: Failed Subscription Operations<p><p>The number of failed subscription operations (Subscribe, Unsubscribe). This metric is incremented for every topic filter within a subscription request. |`Mqtt.FailedSubscriptionOperations` |Count |Total |Protocol, OperationType, Error |Yes|
|MQTT: Request Count<p><p>The number of MQTT requests. |`Mqtt.RequestCount` |Count |Total |OperationType, Protocol, Error, Result |Yes|
|MQTT: Successful Delivered Messages<p><p>The number of messages delivered by the namespace. There are no failures for this operation. |`Mqtt.SuccessfulDeliveredMessages` |Count |Total |QoS, Protocol |Yes|
|MQTT: Successful Published Messages<p><p>The number of  MQTT messages that were published successfully into the namespace. |`Mqtt.SuccessfulPublishedMessages` |Count |Total |QoS, Protocol |Yes|
|MQTT: Successful Subscription Operations<p><p>The number of successful subscription operations (Subscribe, Unsubscribe). This metric is incremented for every topic filter within a subscription request. |`Mqtt.SuccessfulSubscriptionOperations` |Count |Total |Protocol, OperationType |Yes|
|MQTT: Throughput<p><p>The number of bytes published to or delivered by the namespace. |`Mqtt.Throughput` |Bytes |Total |Direction |Yes|
|Publish Operations Latency<p><p>The observed latency in milliseconds for publish events operation. |`PublishLatencyInMilliseconds` |Milliseconds |Total |Topic |No|
|Receive Operations Latency<p><p>The observed latency in milliseconds for receive events operation. |`ReceiveLatencyInMilliseconds` |Milliseconds |Total |Topic, EventSubscriptionName |No|
|Reject Operations Latency<p><p>The observed latency in milliseconds for reject events operation. |`RejectLatencyInMilliseconds` |Milliseconds |Total |Topic, EventSubscriptionName |No|
|Successful Acknowledged Events<p><p>The number of events for which delivery was successfully acknowledged by clients. |`SuccessfulAcknowledgedEvents` |Count |Total |Topic, EventSubscriptionName |No|
|Successful Publish Events<p><p>The number of events published successfully to a topic or topic space within a namespace. |`SuccessfulPublishedEvents` |Count |Total |Topic |No|
|Successful Received Events<p><p>The total number of events that were successfully returned to (received by) clients by Event Grid. |`SuccessfulReceivedEvents` |Count |Total |Topic, EventSubscriptionName |No|
|Successful Released Events<p><p>The number of events that were released successfully by queue subscriber clients. |`SuccessfulReleasedEvents` |Count |Total |Topic, EventSubscriptionName |No|


<!--Gen Date:  Thu Jul 13 2023 10:39:46 GMT+0300 (Israel Daylight Time)-->