---
title: Azure Monitor Logs reference - CDBCassandraRequests
description: Reference for CDBCassandraRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/29/2022
---

# CDBCassandraRequests

 This table details data plane operations, specifically for Azure Cosmos DB for Apache Cassandra accounts.

## Solutions

- LogManagement

## Resource types

- Azure Cosmos DB

## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountName | string | The name of the Azure Cosmos DB account against which this request was issued. |
| ActivityId | string | The unique identifier (GUID) for this request. |
| Address | string | The IP address of the client that issued this request. |
| AuthorizationTokenType | string | The authorization token used for this request. |
| CollectionName | string | The name of the Azure Cosmos DB table/container against which this request was issued. |
| DatabaseName | string | The name of the Azure Cosmos DB database against which this request was issued. |
| DurationMs | real | The server side execution time (in ms) for this request. |
| ErrorCode | string | The error code (if applicable) for this request. |
| OperationName | string | The operation that was executed. |
| PIICommandText | string | Full query text with parameters (if opted in) for this request. |
| RateLimitingDelayMs | real | The estimated time (in ms) spent in retrying due to rate limited operations. |
| RegionName | string | The region against which this request was issued. |
| RequestCharge | real | The RU (Request Unit) consumption for this request. |
| RequestLength | real | The payload size (in bytes) of the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseLength | real | The payload size (in bytes) of the server response. |
| RetriedDueToRateLimiting | bool | Boolean flag indicating if this request was retried server side due to throttles. |
| RetryCount | int | The number of server side retries issued for this request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) of the data plane request. |
| Type | string | The name of the table |
| UserAgent | string | The user agent suffix of the client issuing the request. |
