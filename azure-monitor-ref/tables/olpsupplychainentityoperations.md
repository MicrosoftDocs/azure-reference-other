---
title: Azure Monitor Logs reference - OLPSupplyChainEntityOperations
description: Reference for OLPSupplyChainEntityOperations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# OLPSupplyChainEntityOperations

 The OLPSupplyChainEntityOperations table captures every data plane operation performed on a supplychain entity in the workspace. Data Plane requests are operations executed to create, update, delete or retrieve supplychain entities such as Warehouse, Item, DeliveryNode, Shipment etc. within a workspace.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft.OpenLogisticsPlatform/Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClientApplicationId | string | Application ID of the client making the API request. |
| ClientName | string | Name of the client making the API request. |
| ClientObjectId | string | Object ID of the client making the API request. |
| ClientTenantId | string | Tenant ID of the client making the API request. |
| CorrelationId | string | Unique identifier to be used to correlate logs. |
| CustomRequestAttributes | dynamic | Client defined arbitrary data in the API request. |
| DurationMs | real | Time it took to service the REST API request, in milliseconds. |
| HttpStatusCode | int | HTTP status code of the API response. |
| OperationName | string | The operation name for which the log entry was created. |
| RequestBody | dynamic | Request body of the API calls. |
| RequestId | string | Unique identifier to be used to correlate request logs. |
| RequestMethod | string | HTTP method of the API request. |
| RequestUri | string | URI of the API request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseBody | dynamic | Request body of the API calls. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
