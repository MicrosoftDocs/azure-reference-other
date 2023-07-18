---
title: Supported metrics - Microsoft.DigitalTwins/digitalTwinsInstances
description: Reference for Microsoft.DigitalTwins/digitalTwinsInstances metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DigitalTwins/digitalTwinsInstances  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.DigitalTwins/digitalTwinsInstances resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|API Requests<p><p>The number of API requests made for Digital Twins read, write, delete and query operations. |`ApiRequests` |Count |Total |Operation, Authentication, Protocol, StatusCode, StatusCodeClass, StatusText |Yes|
|API Requests Failure Rate<p><p>The percentage of API requests that the service receives for your instance that return an internal error (500) response code for Digital Twins read, write, delete and query operations. |`ApiRequestsFailureRate` |Percent |Average |Operation, Authentication, Protocol |Yes|
|API Requests Latency<p><p>The response time for API requests, i.e. from when the request is received by Azure Digital Twins until the service sends a success/fail result for Digital Twins read, write, delete and query operations. |`ApiRequestsLatency` |Milliseconds |Average |Operation, Authentication, Protocol, StatusCode, StatusCodeClass, StatusText |Yes|
|Billing API Operations<p><p>Billing metric for the count of all API requests made against the Azure Digital Twins service. |`BillingApiOperations` |Count |Total |MeterId |Yes|
|Billing Messages Processed<p><p>Billing metric for the number of messages sent out from Azure Digital Twins to external endpoints. |`BillingMessagesProcessed` |Count |Total |MeterId |Yes|
|Billing Query Units<p><p>The number of Query Units, an internally computed measure of service resource usage, consumed to execute queries. |`BillingQueryUnits` |Count |Total |MeterId |Yes|
|Bulk Operation Entity Count (preview)<p><p>The number of twins, models, or relationships processed by a bulk operation. |`BulkOperationEntityCount` |Count |Total |Operation, Result |Yes|
|Bulk Operation Latency (preview)<p><p>Total time taken for a bulk operation to complete. |`BulkOperationLatency` |Milliseconds |Average |Operation, Authentication, Protocol |Yes|
|Data History Messages Routed (preview)<p><p>The number of messages routed to a time series database. |`DataHistoryRouting` |Count |Total |EndpointType, Result |Yes|
|Data History Routing Failure Rate (preview)<p><p>The percentage of events that result in an error as they are routed from Azure Digital Twins to a time series database. |`DataHistoryRoutingFailureRate` |Percent |Average |EndpointType |Yes|
|Data History Routing Latency (preview)<p><p>Time elapsed between an event getting routed from Azure Digital Twins to when it is posted to a time series database. |`DataHistoryRoutingLatency` |Milliseconds |Average |EndpointType, Result |Yes|
|Ingress Events<p><p>The number of incoming telemetry events into Azure Digital Twins. |`IngressEvents` |Count |Total |Result |Yes|
|Ingress Events Failure Rate<p><p>The percentage of incoming telemetry events for which the service returns an internal error (500) response code. |`IngressEventsFailureRate` |Percent |Average |No Dimensions |Yes|
|Ingress Events Latency<p><p>The time from when an event arrives to when it is ready to be egressed by Azure Digital Twins, at which point the service sends a success/fail result. |`IngressEventsLatency` |Milliseconds |Average |Result |Yes|
|Model Count<p><p>Total number of models in the Azure Digital Twins instance. Use this metric to determine if you are approaching the service limit for max number of models allowed per instance. |`ModelCount` |Count |Total |No Dimensions |Yes|
|Messages Routed<p><p>The number of messages routed to an endpoint Azure service such as Event Hub, Service Bus or Event Grid. |`Routing` |Count |Total |EndpointType, Result |Yes|
|Routing Failure Rate<p><p>The percentage of events that result in an error as they are routed from Azure Digital Twins to an endpoint Azure service such as Event Hub, Service Bus or Event Grid. |`RoutingFailureRate` |Percent |Average |EndpointType |Yes|
|Routing Latency<p><p>Time elapsed between an event getting routed from Azure Digital Twins to when it is posted to the endpoint Azure service such as Event Hub, Service Bus or Event Grid. |`RoutingLatency` |Milliseconds |Average |EndpointType, Result |Yes|
|Twin Count<p><p>Total number of twins in the Azure Digital Twins instance. Use this metric to determine if you are approaching the service limit for max number of twins allowed per instance. |`TwinCount` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->