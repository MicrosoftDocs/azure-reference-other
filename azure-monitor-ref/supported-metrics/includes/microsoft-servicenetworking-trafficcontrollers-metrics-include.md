---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.ServiceNetworking/trafficControllers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Backend Connection Timeouts**<br><br>Count of requests that timed out waiting for a response from the backend target (includes all retry requests initiated from Application Gateway for Containers to the backend target) |`BackendConnectionTimeouts` |Count |Total |`Microsoft.regionName`, `BackendService`|PT1M |Yes|
|**Backend Healthy Targets**<br><br>Count of healthy backend targets |`BackendHealthyTargets` |Count |Average |`Microsoft.regionName`, `BackendService`|PT1M |Yes|
|**Backend HTTP Response Status**<br><br>HTTP response status returned by the backend target to Application Gateway for Containers |`BackendHTTPResponseStatus` |Count |Total |`Microsoft.regionName`, `BackendService`, `HttpResponseCode`|PT1M |Yes|
|**Total Connection Idle Timeouts**<br><br>Count of connections closed, between client and Application Gateway for Containers frontend, due to exceeding idle timeout |`ClientConnectionIdleTimeouts` |Count |Total |`Microsoft.regionName`, `Frontend`|PT1M |Yes|
|**Connection Timeouts**<br><br>Count of connections closed due to timeout between clients and Application Gateway for Containers |`ConnectionTimeouts` |Count |Total |`Microsoft.regionName`, `Frontend`|PT1M |Yes|
|**HTTP Response Status**<br><br>HTTP response status returned by Application Gateway for Containers |`HTTPResponseStatus` |Count |Total |`Microsoft.regionName`, `Frontend`, `HttpResponseCode`|PT1M |Yes|
|**Total Requests**<br><br>Count of requests Application Gateway for Containers has served |`TotalRequests` |Count |Total |`Microsoft.regionName`, `Frontend`|PT1M |Yes|