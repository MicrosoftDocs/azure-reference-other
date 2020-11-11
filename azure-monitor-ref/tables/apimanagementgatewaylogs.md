---
title: Azure Monitor Logs reference - ApiManagementGatewayLogs
description: Reference for ApiManagementGatewayLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 10/26/2020
---

# ApiManagementGatewayLogs

 Azure ApiManagement Gateway Logs

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- API Management services




## Columns

|Column|Type|Description|
|---|---|---|
|ApiId|string||
|ApimSubscriptionId|string||
|ApiRevision|string||
|BackendId|string||
|BackendMethod|string||
|BackendProtocol|string||
|BackendRequestHeaders|dynamic|An object of all traced backend request headers. Note: Enable header logging in Api > Settings > Diagnostic Logs|
|BackendResponseCode|int||
|BackendResponseHeaders|dynamic|An object of all traced backend response headers. Note: Enable header logging in Api > Settings > Diagnostic Logs|
|BackendTime|long||
|BackendUrl|string||
|Cache|string||
|CacheTime|long||
|CallerIpAddress|string||
|Category|string||
|ClientProtocol|string||
|ClientTime|long||
|ClientTlsVersion|string||
|CorrelationId|string||
|Errors|dynamic||
|IsRequestSuccess|bool||
|LastErrorElapsed|long||
|LastErrorMessage|string||
|LastErrorReason|string||
|LastErrorScope|string||
|LastErrorSection|string||
|LastErrorSource|string||
|Method|string||
|OperationId|string||
|OperationName|string||
|ProductId|string||
|Region|string||
|RequestHeaders|dynamic|An object of all traced request headers. Note: Enable header logging in Api > Settings > Diagnostic Logs|
|RequestSize|int||
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResponseCode|int||
|ResponseHeaders|dynamic|An object of all traced response headers. Note: Enable header logging in Api > Settings > Diagnostic Logs|
|ResponseSize|int||
|SourceSystem|string||
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TenantId|string||
|TimeGenerated|datetime||
|TotalTime|long||
|Type|string|The name of the table|
|Url|string||
|UserId|string||
