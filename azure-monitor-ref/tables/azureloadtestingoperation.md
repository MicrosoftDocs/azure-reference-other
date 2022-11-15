---
title: Azure Monitor Logs reference - AzureLoadTestingOperation
description: Reference for AzureLoadTestingOperation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# AzureLoadTestingOperation

 Details about the operations which are performed on the Azure Load Testing resource. For example, operations like creation of a Test, Test run etc.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Azure Load Testing




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIpAddress | string | IP Address of the client that submitted the request. |
| CorrelationId | string | Unique identifier to be used to correlate logs. |
| DurationMs | real | Amount of time it took to process request in milliseconds. |
| FailureDetails | string | Details of the error in case if request is failed. |
| HttpStatusCode | int | HTTP status code of the API response. |
| Identity | dynamic | JSON structure containing information about the caller. |
| OperationId | string | Operation identifier for rest api |
| OperationName | string | Name of the operation attempted on the resource. |
| OperationVersion | string | Request api version |
| RequestBody | dynamic | Request body of the API calls. |
| RequestId | string | Unique identifier to be used to correlate request logs. |
| RequestMethod | string | HTTP method of the API request. |
| RequestUri | string | URI of the API request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceRegion | string | Region where the resource is located. |
| ResultType | string | Indicates if the request was successful or failed. |
| ServiceLocation | string | Location of the service which processed the request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
| UserAgent | string | HTTP header passed by the client, if applicable. |
