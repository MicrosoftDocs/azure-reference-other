---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Communication/CommunicationServices, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Authentication API Requests**<br><br>Count of all requests against the Communication Services Authentication endpoint. |`APIRequestAuthentication` |Count |Count |`Operation`, `StatusCode`, `StatusCodeClass`|PT1M |No|
|Traffic|**Call Automation API Requests**<br><br>Count of all requests against the Communication Call Automation endpoint. |`APIRequestCallAutomation` |Count |Count |`Operation`, `StatusCode`, `StatusCodeClass`, `ApiVersion`|PT1M |Yes|
|Traffic|**Call Recording API Requests**<br><br>Count of all requests against the Communication Services Call Recording endpoint. |`APIRequestCallRecording` |Count |Count |`Operation`, `StatusCode`, `StatusCodeClass`|PT1M |Yes|
|Traffic|**Chat API Requests**<br><br>Count of all requests against the Communication Services Chat endpoint. |`APIRequestChat` |Count |Count |`Operation`, `StatusCode`, `StatusCodeClass`|PT1M |Yes|
|Traffic|**Network Traversal API Requests**<br><br>Count of all requests against the Communication Services Network Traversal endpoint. |`APIRequestNetworkTraversal` |Count |Count |`Operation`, `StatusCode`, `StatusCodeClass`|PT1M |No|
|Traffic|**Rooms API Requests**<br><br>Count of all requests against the Communication Services Rooms endpoint. |`ApiRequestRooms` |Count |Count |`Operation`, `StatusCode`, `StatusCodeClass`|PT1M |Yes|
|Traffic|**Job Router API Requests**<br><br>Count of all requests against the Communication Services Job Router endpoint. |`ApiRequestRouter` |Count |Count |`OperationName`, `StatusCode`, `StatusCodeSubClass`, `ApiVersion`|PT1M |Yes|
|Traffic|**Email Service API Requests**<br><br>Email Communication Services API request metric for the data-plane API surface. |`ApiRequests` |Count |Count |`Operation`, `StatusCode`, `StatusCodeClass`, `StatusCodeReason`|PT1M |Yes|
|Traffic|**Advanced Messaging API Requests**<br><br>Count of all requests against the Communication Services Advanced Messaging endpoint. |`APIRequestsAdvancedMessaging` |Count |Count |`Operation`, `StatusCode`, `StatusCodeClass`, `ChannelType`, `ApiVersion`, `MessageStatus`|PT1M |Yes|
|Traffic|**SMS API Requests**<br><br>Count of all requests against the Communication Services SMS endpoint. |`APIRequestSMS` |Count |Count |`Operation`, `StatusCode`, `StatusCodeClass`, `ErrorCode`, `NumberType`, `Country`, `OptAction`|PT1M |Yes|
|Traffic|**Email Service Delivery Status Updates**<br><br>Email Communication Services message delivery results. |`DeliveryStatusUpdate` |Count |Count |`MessageStatus`, `Result`, `SmtpStatusCode`, `EnhancedSmtpStatusCode`, `SenderDomain`, `IsHardBounce`|PT1M |Yes|
|Traffic|**Email Service User Engagement**<br><br>Email Communication Services user engagement metrics. |`UserEngagement` |Count |Count |`EngagementType`|PT1M |Yes|