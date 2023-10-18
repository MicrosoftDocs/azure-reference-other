---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ApiManagement/service, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Duration of Backend Requests**<p><p>Duration of Backend Requests in milliseconds |`BackendDuration` |MilliSeconds |Average, Maximum, Minimum |`Location`, `Hostname`|PT1M |Yes|
|**Capacity**<p><p>Utilization metric for ApiManagement service. Note: For skus other than Premium, 'Max' aggregation will show the value as 0. |`Capacity` |Percent |Average, Maximum |`Location`|PT1M |Yes|
|**WebSocket Connection Attempts (Preview)**<p><p>Count of WebSocket connection attempts based on selected source and destination |`ConnectionAttempts` |Count |Total, Average |`Location`, `Source`, `Destination`, `State`|PT1M |Yes|
|**Overall Duration of Gateway Requests**<p><p>Overall Duration of Gateway Requests in milliseconds |`Duration` |MilliSeconds |Average, Maximum, Minimum |`Location`, `Hostname`|PT1M |Yes|
|**Dropped EventHub Events**<p><p>Number of events skipped because of queue size limit reached |`EventHubDroppedEvents` |Count |Total |`Location`|PT1M |Yes|
|**Rejected EventHub Events**<p><p>Number of rejected EventHub events (wrong configuration or unauthorized) |`EventHubRejectedEvents` |Count |Total |`Location`|PT1M |Yes|
|**Successful EventHub Events**<p><p>Number of successful EventHub events |`EventHubSuccessfulEvents` |Count |Total |`Location`|PT1M |Yes|
|**Throttled EventHub Events**<p><p>Number of throttled EventHub events |`EventHubThrottledEvents` |Count |Total |`Location`|PT1M |Yes|
|**Timed Out EventHub Events**<p><p>Number of timed out EventHub events |`EventHubTimedoutEvents` |Count |Total |`Location`|PT1M |Yes|
|**Size of EventHub Events**<p><p>Total size of EventHub events in bytes |`EventHubTotalBytesSent` |Bytes |Total |`Location`|PT1M |Yes|
|**Total EventHub Events**<p><p>Number of events sent to EventHub |`EventHubTotalEvents` |Count |Total |`Location`|PT1M |Yes|
|**Failed EventHub Events**<p><p>Number of failed EventHub events |`EventHubTotalFailedEvents` |Count |Total |`Location`|PT1M |Yes|
|**Failed Gateway Requests (Deprecated)**<p><p>Number of failures in gateway requests - Use multi-dimension request metric with GatewayResponseCodeCategory dimension instead |`FailedRequests` |Count |Total |`Location`, `Hostname`|PT1M |Yes|
|**Network Connectivity Status of Resources (Preview)**<p><p>Network Connectivity status of dependent resource types from API Management service |`NetworkConnectivity` |Count |Total, Average |`Location`, `ResourceType`|PT1M |Yes|
|**Other Gateway Requests (Deprecated)**<p><p>Number of other gateway requests - Use multi-dimension request metric with GatewayResponseCodeCategory dimension instead |`OtherRequests` |Count |Total |`Location`, `Hostname`|PT1M |Yes|
|**Requests**<p><p>Gateway request metrics with multiple dimensions |`Requests` |Count |Total, Maximum, Minimum |`Location`, `Hostname`, `LastErrorReason`, `BackendResponseCode`, `GatewayResponseCode`, `BackendResponseCodeCategory`, `GatewayResponseCodeCategory`|PT1M |Yes|
|**Successful Gateway Requests (Deprecated)**<p><p>Number of successful gateway requests - Use multi-dimension request metric with GatewayResponseCodeCategory dimension instead |`SuccessfulRequests` |Count |Total |`Location`, `Hostname`|PT1M |Yes|
|**Total Gateway Requests (Deprecated)**<p><p>Number of gateway requests - Use multi-dimension request metric with GatewayResponseCodeCategory dimension instead |`TotalRequests` |Count |Total |`Location`, `Hostname`|PT1M |Yes|
|**Unauthorized Gateway Requests (Deprecated)**<p><p>Number of unauthorized gateway requests - Use multi-dimension request metric with GatewayResponseCodeCategory dimension instead |`UnauthorizedRequests` |Count |Total |`Location`, `Hostname`|PT1M |Yes|
|**WebSocket Messages (Preview)**<p><p>Count of WebSocket messages based on selected source and destination |`WebSocketMessages` |Count |Total, Average |`Location`, `Source`, `Destination`|PT1M |Yes|