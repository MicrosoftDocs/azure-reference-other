---
title: Azure Monitor Logs reference - AgriFoodFarmManagementLogs
description: Reference for AgriFoodFarmManagementLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# AgriFoodFarmManagementLogs

 Logs for create, update, delete and get operations on FarmBeats resources such as Farmer, Farm, Field, Boundary, Seasonal Field, Crop, CropVariety, Season, Attachment, Prescription Maps, Prescriptions, Management Zones, Zones, Plant Tissue Analysis, Nutrient Analysis etc.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft.AgFoodPlatform/farmBeats




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationId | string | ApplicationId in identity claims. |
| CallerIpAddress | string | IP address of the client that made the request. |
| Category | string | Logs generated as a result of operations executed using FarmBeats APIs are grouped into categories. Categories in FarmBeats are logical groupings based on either the data source the underlying APIs fetch data from or on the basis of hierarchy of entities in FarmBeats. |
| ClientTenantId | string | TenantId in identity claims. |
| CorrelationId | string | Unique identifier to be used to correlate logs, when available. |
| DataPlaneResourceId | string | ID that uniquely identifies a FarmBeats resource such as a Farm, Farmer, Boundary etc. |
| DurationMs | real | Time it took to service the REST API request, in milliseconds. |
| FarmerId | string | Farmer ID associated with the request, wherever applicable. |
| Level | string | The severity level of the event, will be one of Informational, Warning, Error, or Critical. |
| Location | string | The region of the resource emitting the event. |
| ObjectId | string | ObjectId in identity claims. |
| OperationName | string | The operation name for which the log entry was created. |
| RequestBody | dynamic | Request body of the API calls. |
| RequestUri | string | URI of the API request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Additional details about the result, when available. |
| ResultSignature | int | HTTP status of API request. |
| ResultType | string | Result of the REST API request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when the log was created. |
| Type | string | The name of the table |
