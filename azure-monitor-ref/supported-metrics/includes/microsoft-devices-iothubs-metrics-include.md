---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Devices/IotHubs, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**C2D messages abandoned**<p><p>Number of cloud-to-device messages abandoned by the device |`c2d.commands.egress.abandon.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**C2D message deliveries completed**<p><p>Number of cloud-to-device message deliveries completed successfully by the device |`c2d.commands.egress.complete.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**C2D messages rejected**<p><p>Number of cloud-to-device messages rejected by the device |`c2d.commands.egress.reject.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Failed direct method invocations**<p><p>The count of all failed direct method calls. |`c2d.methods.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Request size of direct method invocations**<p><p>The average, min, and max of all successful direct method requests. |`c2d.methods.requestSize` |Bytes |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Response size of direct method invocations**<p><p>The average, min, and max of all successful direct method responses. |`c2d.methods.responseSize` |Bytes |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful direct method invocations**<p><p>The count of all successful direct method calls. |`c2d.methods.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Failed twin reads from back end**<p><p>The count of all failed back-end-initiated twin reads. |`c2d.twin.read.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Response size of twin reads from back end**<p><p>The average, min, and max of all successful back-end-initiated twin reads. |`c2d.twin.read.size` |Bytes |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful twin reads from back end**<p><p>The count of all successful back-end-initiated twin reads. |`c2d.twin.read.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Failed twin updates from back end**<p><p>The count of all failed back-end-initiated twin updates. |`c2d.twin.update.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Size of twin updates from back end**<p><p>The average, min, and max size of all successful back-end-initiated twin updates. |`c2d.twin.update.size` |Bytes |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful twin updates from back end**<p><p>The count of all successful back-end-initiated twin updates. |`c2d.twin.update.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**C2D Messages Expired**<p><p>Number of expired cloud-to-device messages |`C2DMessagesExpired` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Configuration Metrics**<p><p>Metrics for Configuration Operations |`configurations` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Connected devices**<p><p>Number of devices connected to your IoT hub |`connectedDeviceCount` |Count |Average, Maximum, Minimum |\<none\>|PT1M |No|
|**Routing: messages delivered to messages/events**<p><p>The number of times IoT Hub routing successfully delivered messages to the built-in endpoint (messages/events). |`d2c.endpoints.egress.builtIn.events` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: messages delivered to Event Hub**<p><p>The number of times IoT Hub routing successfully delivered messages to Event Hub endpoints. |`d2c.endpoints.egress.eventHubs` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: messages delivered to Service Bus Queue**<p><p>The number of times IoT Hub routing successfully delivered messages to Service Bus queue endpoints. |`d2c.endpoints.egress.serviceBusQueues` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: messages delivered to Service Bus Topic**<p><p>The number of times IoT Hub routing successfully delivered messages to Service Bus topic endpoints. |`d2c.endpoints.egress.serviceBusTopics` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: messages delivered to storage**<p><p>The number of times IoT Hub routing successfully delivered messages to storage endpoints. |`d2c.endpoints.egress.storage` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: blobs delivered to storage**<p><p>The number of times IoT Hub routing delivered blobs to storage endpoints. |`d2c.endpoints.egress.storage.blobs` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: data delivered to storage**<p><p>The amount of data (bytes) IoT Hub routing delivered to storage endpoints. |`d2c.endpoints.egress.storage.bytes` |Bytes |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: message latency for messages/events**<p><p>The average latency (milliseconds) between message ingress to IoT Hub and telemetry message ingress into the built-in endpoint (messages/events). |`d2c.endpoints.latency.builtIn.events` |MilliSeconds |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Routing: message latency for Event Hub**<p><p>The average latency (milliseconds) between message ingress to IoT Hub and message ingress into an Event Hub endpoint. |`d2c.endpoints.latency.eventHubs` |MilliSeconds |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Routing: message latency for Service Bus Queue**<p><p>The average latency (milliseconds) between message ingress to IoT Hub and telemetry message ingress into a Service Bus queue endpoint. |`d2c.endpoints.latency.serviceBusQueues` |MilliSeconds |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Routing: message latency for Service Bus Topic**<p><p>The average latency (milliseconds) between message ingress to IoT Hub and telemetry message ingress into a Service Bus topic endpoint. |`d2c.endpoints.latency.serviceBusTopics` |MilliSeconds |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Routing: message latency for storage**<p><p>The average latency (milliseconds) between message ingress to IoT Hub and telemetry message ingress into a storage endpoint. |`d2c.endpoints.latency.storage` |MilliSeconds |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Routing: telemetry messages dropped**<p><p>The number of times messages were dropped by IoT Hub routing due to dead endpoints. This value does not count messages delivered to fallback route as dropped messages are not delivered there. |`d2c.telemetry.egress.dropped` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: messages delivered to fallback**<p><p>The number of times IoT Hub routing delivered messages to the endpoint associated with the fallback route. |`d2c.telemetry.egress.fallback` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: telemetry messages incompatible**<p><p>The number of times IoT Hub routing failed to deliver messages due to an incompatibility with the endpoint. This value does not include retries. |`d2c.telemetry.egress.invalid` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: telemetry messages orphaned**<p><p>The number of times messages were orphaned by IoT Hub routing because they didn't match any routing rules (including the fallback rule).  |`d2c.telemetry.egress.orphaned` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing: telemetry messages delivered**<p><p>The number of times messages were successfully delivered to all endpoints using IoT Hub routing. If a message is routed to multiple endpoints, this value increases by one for each successful delivery. If a message is delivered to the same endpoint multiple times, this value increases by one for each successful delivery. |`d2c.telemetry.egress.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Telemetry message send attempts**<p><p>Number of device-to-cloud telemetry messages attempted to be sent to your IoT hub |`d2c.telemetry.ingress.allProtocol` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Number of throttling errors**<p><p>Number of throttling errors due to device throughput throttles |`d2c.telemetry.ingress.sendThrottle` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Telemetry messages sent**<p><p>Number of device-to-cloud telemetry messages sent successfully to your IoT hub |`d2c.telemetry.ingress.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Failed twin reads from devices**<p><p>The count of all failed device-initiated twin reads. |`d2c.twin.read.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Response size of twin reads from devices**<p><p>The average, min, and max of all successful device-initiated twin reads. |`d2c.twin.read.size` |Bytes |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful twin reads from devices**<p><p>The count of all successful device-initiated twin reads. |`d2c.twin.read.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Failed twin updates from devices**<p><p>The count of all failed device-initiated twin updates. |`d2c.twin.update.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Size of twin updates from devices**<p><p>The average, min, and max size of all successful device-initiated twin updates. |`d2c.twin.update.size` |Bytes |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful twin updates from devices**<p><p>The count of all successful device-initiated twin updates. |`d2c.twin.update.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Total number of messages used**<p><p>Number of total messages used today |`dailyMessageQuotaUsed` |Count |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Total device data usage**<p><p>Bytes transferred to and from any devices connected to IotHub |`deviceDataUsage` |Bytes |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Total device data usage (preview)**<p><p>Bytes transferred to and from any devices connected to IotHub |`deviceDataUsageV2` |Bytes |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Connected devices (deprecated)**<p><p>Number of devices connected to your IoT hub |`devices.connectedDevices.allProtocol` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Total devices (deprecated)**<p><p>Number of devices registered to your IoT hub |`devices.totalDevices` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Event Grid deliveries**<p><p>The number of IoT Hub events published to Event Grid. Use the Result dimension for the number of successful and failed requests. EventType dimension shows the type of event (https://aka.ms/ioteventgrid). |`EventGridDeliveries` |Count |Average, Minimum, Maximum, Total |`Result`, `EventType`|PT1M |Yes|
|**Event Grid latency**<p><p>The average latency (milliseconds) from when the Iot Hub event was generated to when the event was published to Event Grid. This number is an average between all event types. Use the EventType dimension to see latency of a specific type of event. |`EventGridLatency` |MilliSeconds |Average, Minimum, Maximum |`EventType`|PT1M |Yes|
|**Failed job cancellations**<p><p>The count of all failed calls to cancel a job. |`jobs.cancelJob.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful job cancellations**<p><p>The count of all successful calls to cancel a job. |`jobs.cancelJob.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Completed jobs**<p><p>The count of all completed jobs. |`jobs.completed` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Failed creations of method invocation jobs**<p><p>The count of all failed creation of direct method invocation jobs. |`jobs.createDirectMethodJob.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful creations of method invocation jobs**<p><p>The count of all successful creation of direct method invocation jobs. |`jobs.createDirectMethodJob.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Failed creations of twin update jobs**<p><p>The count of all failed creation of twin update jobs. |`jobs.createTwinUpdateJob.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful creations of twin update jobs**<p><p>The count of all successful creation of twin update jobs. |`jobs.createTwinUpdateJob.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Failed jobs**<p><p>The count of all failed jobs. |`jobs.failed` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Failed calls to list jobs**<p><p>The count of all failed calls to list jobs. |`jobs.listJobs.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful calls to list jobs**<p><p>The count of all successful calls to list jobs. |`jobs.listJobs.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Failed job queries**<p><p>The count of all failed calls to query jobs. |`jobs.queryJobs.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful job queries**<p><p>The count of all successful calls to query jobs. |`jobs.queryJobs.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Routing Delivery Message Size in Bytes (preview)**<p><p>The total size in bytes of messages delivered by IoT hub to an endpoint. You can use the EndpointName and EndpointType dimensions to view the size of the messages in bytes delivered to your different endpoints. The metric value increases for every message delivered, including if the message is delivered to multiple endpoints or if the message is delivered to the same endpoint multiple times. |`RoutingDataSizeInBytesDelivered` |Bytes |Average, Minimum, Maximum, Total |`EndpointType`, `EndpointName`, `RoutingSource`|PT1M |Yes|
|**Routing Deliveries (preview)**<p><p>The number of times IoT Hub attempted to deliver messages to all endpoints using routing. To see the number of successful or failed attempts, use the Result dimension. To see the reason of failure, like invalid, dropped, or orphaned, use the FailureReasonCategory dimension. You can also use the EndpointName and EndpointType dimensions to understand how many messages were delivered to your different endpoints. The metric value increases by one for each delivery attempt, including if the message is delivered to multiple endpoints or if the message is delivered to the same endpoint multiple times. |`RoutingDeliveries` |Count |Average, Minimum, Maximum, Total |`EndpointType`, `EndpointName`, `FailureReasonCategory`, `Result`, `RoutingSource`|PT1M |Yes|
|**Routing Delivery Latency (preview)**<p><p>The average latency (milliseconds) between message ingress to IoT Hub and telemetry message ingress into an endpoint. You can use the EndpointName and EndpointType dimensions to understand the latency to your different endpoints. |`RoutingDeliveryLatency` |MilliSeconds |Average, Minimum, Maximum |`EndpointType`, `EndpointName`, `RoutingSource`|PT1M |Yes|
|**Total devices**<p><p>Number of devices registered to your IoT hub |`totalDeviceCount` |Count |Average, Maximum, Minimum |\<none\>|PT1M |No|
|**Failed twin queries**<p><p>The count of all failed twin queries. |`twinQueries.failure` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Twin queries result size**<p><p>The average, min, and max of the result size of all successful twin queries. |`twinQueries.resultSize` |Bytes |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Successful twin queries**<p><p>The count of all successful twin queries. |`twinQueries.success` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|