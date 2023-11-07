---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/29/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DigitalTwins/digitalTwinsInstances, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**API Requests**<p><p>The number of API requests made for Digital Twins read, write, delete and query operations. |`ApiRequests` |Count |Total |`Operation`, `Authentication`, `Protocol`, `StatusCode`, `StatusCodeClass`, `StatusText`|PT1M |Yes|
|**API Requests Failure Rate**<p><p>The percentage of API requests that the service receives for your instance that return an internal error (500) response code for Digital Twins read, write, delete and query operations. |`ApiRequestsFailureRate` |Percent |Average |`Operation`, `Authentication`, `Protocol`|PT1M |Yes|
|**API Requests Latency**<p><p>The response time for API requests, i.e. from when the request is received by Azure Digital Twins until the service sends a success/fail result for Digital Twins read, write, delete and query operations. |`ApiRequestsLatency` |Milliseconds |Average, Minimum, Maximum, Total |`Operation`, `Authentication`, `Protocol`, `StatusCode`, `StatusCodeClass`, `StatusText`|PT1M |Yes|
|**Billing API Operations**<p><p>Billing metric for the count of all API requests made against the Azure Digital Twins service. |`BillingApiOperations` |Count |Average, Minimum, Maximum, Total |`MeterId`|PT1M |Yes|
|**Billing Messages Processed**<p><p>Billing metric for the number of messages sent out from Azure Digital Twins to external endpoints. |`BillingMessagesProcessed` |Count |Average, Minimum, Maximum, Total |`MeterId`|PT1M |Yes|
|**Billing Query Units**<p><p>The number of Query Units, an internally computed measure of service resource usage, consumed to execute queries. |`BillingQueryUnits` |Count |Average, Minimum, Maximum, Total |`MeterId`|PT1M |Yes|
|**Data History Messages Routed (preview)**<p><p>The number of messages routed to a time series database. |`DataHistoryRouting` |Count |Total |`EndpointType`, `Result`|PT1M |Yes|
|**Data History Routing Failure Rate (preview)**<p><p>The percentage of events that result in an error as they are routed from Azure Digital Twins to a time series database. |`DataHistoryRoutingFailureRate` |Percent |Average |`EndpointType`|PT1M |Yes|
|**Data History Routing Latency (preview)**<p><p>Time elapsed between an event getting routed from Azure Digital Twins to when it is posted to a time series database. |`DataHistoryRoutingLatency` |Milliseconds |Average, Minimum, Maximum, Total |`EndpointType`, `Result`|PT1M |Yes|
|**Delete Job Entity Count**<p><p>The number of models, twins, and relationships deleted by a delete job. |`DeleteJobEntityCount` |Count |Average, Minimum, Maximum, Total |`Operation`, `Result`|PT1M |Yes|
|**Delete Job Latency**<p><p>Total time taken for a delete job to complete. |`DeleteJobLatency` |Milliseconds |Average, Minimum, Maximum, Total |`Operation`, `Authentication`, `Protocol`|PT1M |Yes|
|**Import Job Entity Count**<p><p>The number of twins, models, or relationships processed by an import job. |`ImportJobEntityCount` |Count |Average, Minimum, Maximum, Total |`Operation`, `Result`|PT1M |Yes|
|**Import Job Latency**<p><p>Total time taken for an import job to complete. |`ImportJobLatency` |Milliseconds |Average, Minimum, Maximum, Total |`Operation`, `Authentication`, `Protocol`|PT1M |Yes|
|**Ingress Events**<p><p>The number of incoming telemetry events into Azure Digital Twins. |`IngressEvents` |Count |Total |`Result`|PT1M |Yes|
|**Ingress Events Failure Rate**<p><p>The percentage of incoming telemetry events for which the service returns an internal error (500) response code. |`IngressEventsFailureRate` |Percent |Average |\<none\>|PT1M |Yes|
|**Ingress Events Latency**<p><p>The time from when an event arrives to when it is ready to be egressed by Azure Digital Twins, at which point the service sends a success/fail result. |`IngressEventsLatency` |Milliseconds |Average, Minimum, Maximum, Total |`Result`|PT1M |Yes|
|**Model Count**<p><p>Total number of models in the Azure Digital Twins instance. Use this metric to determine if you are approaching the service limit for max number of models allowed per instance. |`ModelCount` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|
|**Messages Routed**<p><p>The number of messages routed to an endpoint Azure service such as Event Hub, Service Bus or Event Grid. |`Routing` |Count |Total |`EndpointType`, `Result`|PT1M |Yes|
|**Routing Failure Rate**<p><p>The percentage of events that result in an error as they are routed from Azure Digital Twins to an endpoint Azure service such as Event Hub, Service Bus or Event Grid. |`RoutingFailureRate` |Percent |Average |`EndpointType`|PT1M |Yes|
|**Routing Latency**<p><p>Time elapsed between an event getting routed from Azure Digital Twins to when it is posted to the endpoint Azure service such as Event Hub, Service Bus or Event Grid. |`RoutingLatency` |Milliseconds |Average, Minimum, Maximum, Total |`EndpointType`, `Result`|PT1M |Yes|
|**Twin Count**<p><p>Total number of twins in the Azure Digital Twins instance. Use this metric to determine if you are approaching the service limit for max number of twins allowed per instance. |`TwinCount` |Count |Average, Minimum, Maximum, Total |\<none\>|PT1M |Yes|