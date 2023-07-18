---
title: Supported metrics - Microsoft.Communication/CommunicationServices
description: Reference for Microsoft.Communication/CommunicationServices metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Communication/CommunicationServices  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Communication/CommunicationServices resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Authentication API Requests<p><p>Count of all requests against the Communication Services Authentication endpoint. |`APIRequestAuthentication` |Count |Count |Operation, StatusCode, StatusCodeClass |No|
|Call Automation API Requests<p><p>Count of all requests against the Communication Call Automation endpoint. |`APIRequestCallAutomation` |Count |Count |Operation, StatusCode, StatusCodeClass |Yes|
|Call Recording API Requests<p><p>Count of all requests against the Communication Services Call Recording endpoint. |`APIRequestCallRecording` |Count |Count |Operation, StatusCode, StatusCodeClass |Yes|
|Chat API Requests<p><p>Count of all requests against the Communication Services Chat endpoint. |`APIRequestChat` |Count |Count |Operation, StatusCode, StatusCodeClass |Yes|
|Network Traversal API Requests<p><p>Count of all requests against the Communication Services Network Traversal endpoint. |`APIRequestNetworkTraversal` |Count |Count |Operation, StatusCode, StatusCodeClass |No|
|Rooms API Requests<p><p>Count of all requests against the Communication Services Rooms endpoint. |`ApiRequestRooms` |Count |Count |Operation, StatusCode, StatusCodeClass |Yes|
|Job Router API Requests<p><p>Count of all requests against the Communication Services Job Router endpoint. |`ApiRequestRouter` |Count |Count |OperationName, StatusCode, StatusCodeSubClass, ApiVersion |Yes|
|Email Service API Requests<p><p>Email Communication Services API request metric for the data-plane API surface. |`ApiRequests` |Count |Count |Operation, StatusCode, StatusCodeClass, StatusCodeReason |Yes|
|SMS API Requests<p><p>Count of all requests against the Communication Services SMS endpoint. |`APIRequestSMS` |Count |Count |Operation, StatusCode, StatusCodeClass, ErrorCode, NumberType, Country, OptAction |Yes|
|Email Service Delivery Status Updates<p><p>Email Communication Services message delivery results. |`DeliveryStatusUpdate` |Count |Count |MessageStatus, Result, SmtpStatusCode, EnhancedSmtpStatusCode, SenderDomain, IsHardBounce |Yes|
|Email Service User Engagement<p><p>Email Communication Services user engagement metrics. |`UserEngagement` |Count |Count |EngagementType |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->