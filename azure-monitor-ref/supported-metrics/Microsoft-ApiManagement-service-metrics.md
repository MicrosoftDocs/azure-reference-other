---
title: Supported metrics - Microsoft.ApiManagement/service
description: Reference for Microsoft.ApiManagement/service metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ApiManagement/service  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ApiManagement/service resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Duration of Backend Requests<p><p>Duration of Backend Requests in milliseconds |`BackendDuration` |MilliSeconds |Average |Location, Hostname |Yes|
|Capacity<p><p>Utilization metric for ApiManagement service. Note: For skus other than Premium, 'Max' aggregation will show the value as 0. |`Capacity` |Percent |Average |Location |Yes|
|WebSocket Connection Attempts (Preview)<p><p>Count of WebSocket connection attempts based on selected source and destination |`ConnectionAttempts` |Count |Total |Location, Source, Destination, State |Yes|
|Overall Duration of Gateway Requests<p><p>Overall Duration of Gateway Requests in milliseconds |`Duration` |MilliSeconds |Average |Location, Hostname |Yes|
|Dropped EventHub Events<p><p>Number of events skipped because of queue size limit reached |`EventHubDroppedEvents` |Count |Total |Location |Yes|
|Rejected EventHub Events<p><p>Number of rejected EventHub events (wrong configuration or unauthorized) |`EventHubRejectedEvents` |Count |Total |Location |Yes|
|Successful EventHub Events<p><p>Number of successful EventHub events |`EventHubSuccessfulEvents` |Count |Total |Location |Yes|
|Throttled EventHub Events<p><p>Number of throttled EventHub events |`EventHubThrottledEvents` |Count |Total |Location |Yes|
|Timed Out EventHub Events<p><p>Number of timed out EventHub events |`EventHubTimedoutEvents` |Count |Total |Location |Yes|
|Size of EventHub Events<p><p>Total size of EventHub events in bytes |`EventHubTotalBytesSent` |Bytes |Total |Location |Yes|
|Total EventHub Events<p><p>Number of events sent to EventHub |`EventHubTotalEvents` |Count |Total |Location |Yes|
|Failed EventHub Events<p><p>Number of failed EventHub events |`EventHubTotalFailedEvents` |Count |Total |Location |Yes|
|Failed Gateway Requests (Deprecated)<p><p>Number of failures in gateway requests - Use multi-dimension request metric with GatewayResponseCodeCategory dimension instead |`FailedRequests` |Count |Total |Location, Hostname |Yes|
|Network Connectivity Status of Resources (Preview)<p><p>Network Connectivity status of dependent resource types from API Management service |`NetworkConnectivity` |Count |Average |Location, ResourceType |Yes|
|Other Gateway Requests (Deprecated)<p><p>Number of other gateway requests - Use multi-dimension request metric with GatewayResponseCodeCategory dimension instead |`OtherRequests` |Count |Total |Location, Hostname |Yes|
|Requests<p><p>Gateway request metrics with multiple dimensions |`Requests` |Count |Total |Location, Hostname, LastErrorReason, BackendResponseCode, GatewayResponseCode, BackendResponseCodeCategory, GatewayResponseCodeCategory |Yes|
|Successful Gateway Requests (Deprecated)<p><p>Number of successful gateway requests - Use multi-dimension request metric with GatewayResponseCodeCategory dimension instead |`SuccessfulRequests` |Count |Total |Location, Hostname |Yes|
|Total Gateway Requests (Deprecated)<p><p>Number of gateway requests - Use multi-dimension request metric with GatewayResponseCodeCategory dimension instead |`TotalRequests` |Count |Total |Location, Hostname |Yes|
|Unauthorized Gateway Requests (Deprecated)<p><p>Number of unauthorized gateway requests - Use multi-dimension request metric with GatewayResponseCodeCategory dimension instead |`UnauthorizedRequests` |Count |Total |Location, Hostname |Yes|
|WebSocket Messages (Preview)<p><p>Count of WebSocket messages based on selected source and destination |`WebSocketMessages` |Count |Total |Location, Source, Destination |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->