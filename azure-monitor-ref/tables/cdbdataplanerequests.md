---
title: Azure Monitor Logs reference - CDBDataPlaneRequests
description: Reference for CDBDataPlaneRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# CDBDataPlaneRequests

 The DataPlaneRequests table captures every data plane operation for the Cosmos DB account. Data Plane requests are operations executed to create, update, delete or retrieve data within the account.

## Solutions

- LogManagement
## Resource types

- Azure Cosmos DB




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AadAppliedRoleAssignmentId | string | The ID of the applied role assignment for the caller issuing the data plane request. |
| AadPrincipalId | string | The AAD Principal ID of the caller issuing the data plane request. |
| AccountName | string | The name of the Cosmos DB account. |
| ActivityId | string | The unique identifier (GUID) for this data plane operation |
| AuthTokenType | string | The authorization type (System Read/Write key) for this request by the Cosmos DB Gateway service when running in Gateway mode or using the REST API. |
| ClientIpAddress | string | The IP address of the client VM issuing the request. |
| CollectionName | string | The Cosmos DB container against which the request was issued. |
| ConnectionMode | string | The connection mode used by the client issuing the request – (Direct or Gateway mode). |
| DatabaseName | string | The Cosmos DB database against which the request was issued. |
| DurationMs | real | The server-side execution time (in milliseconds) for this request. |
| KeyType | string | The authorization type (Primary/Secondary Read/Write key) for this request when running in Direct mode. |
| OperationName | string | The specific data plane operation executed against the account. |
| PartitionId | string | The physical partition ID for the Cosmos DB container against which the request was issued. |
| RegionName | string | The Azure region to which this request was issued. |
| RequestCharge | real | The RUs (Request Units) consumed by this operation. |
| RequestLength | real | The payload size (in bytes) for the request. |
| RequestResourceId | string | The ID of the specific Cosmos DB resource within the account against which the data plane request was executed. |
| RequestResourceType | string | The Cosmos DB resource type within the account against which the data plane request was executed, can be one of Database, Collection, Document, Attachment, User, Permission, StoredProcedure, Trigger, UserDefinedFunction, Offer. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceTokenPermissionId | string | The ID of the resource token associated with the resource accessed by this request. |
| ResourceTokenPermissionMode | string | The permission mode of the resource token associated with the resource accessed by this request. |
| ResourceTokenUserRid | string | The user ID associated with the resource token for the resource accessed by this request. |
| ResponseLength | real | The payload size (in bytes) of the server response. |
| SourceSystem | string |  |
| StatusCode | int | The HTTP status code response for the data plane request, highlighting details of the success/failure of the request. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when the data plane request was issued. |
| Type | string | The name of the table |
| UserAgent | string | The name of the user specified user agent suffix (as specified when initializing the Cosmos DB client) when running in Direct mode. |
