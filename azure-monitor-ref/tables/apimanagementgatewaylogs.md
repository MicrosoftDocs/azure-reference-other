---
title: Azure Monitor Logs reference - ApiManagementGatewayLogs
description: Reference for ApiManagementGatewayLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# ApiManagementGatewayLogs

 Azure ApiManagement gateway logs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- API Management services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApiId | string |  |
| ApimSubscriptionId | string |  |
| ApiRevision | string |  |
| BackendId | string |  |
| BackendMethod | string |  |
| BackendProtocol | string |  |
| BackendRequestBody | string | Backend request body |
| BackendRequestHeaders | dynamic |  |
| BackendResponseBody | string | Backend response body |
| BackendResponseCode | int |  |
| BackendResponseHeaders | dynamic |  |
| BackendTime | long |  |
| BackendUrl | string |  |
| Cache | string |  |
| CacheTime | long |  |
| CallerIpAddress | string |  |
| Category | string |  |
| ClientProtocol | string |  |
| ClientTime | long |  |
| ClientTlsVersion | string |  |
| CorrelationId | string |  |
| Errors | dynamic |  |
| IsRequestSuccess | bool |  |
| LastErrorElapsed | long |  |
| LastErrorMessage | string |  |
| LastErrorReason | string |  |
| LastErrorScope | string |  |
| LastErrorSection | string |  |
| LastErrorSource | string |  |
| Method | string |  |
| OperationId | string |  |
| OperationName | string |  |
| ProductId | string |  |
| Region | string |  |
| RequestBody | string | Client request body |
| RequestHeaders | dynamic |  |
| RequestSize | int |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseBody | string | Gateway response body |
| ResponseCode | int |  |
| ResponseHeaders | dynamic |  |
| ResponseSize | int |  |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime |  |
| TotalTime | long |  |
| TraceRecords | dynamic | Records emitted by trace policies |
| Type | string | The name of the table |
| Url | string |  |
| UserId | string |  |
