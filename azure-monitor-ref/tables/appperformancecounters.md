---
title: Azure Monitor Logs reference - AppPerformanceCounters
description: Reference for AppPerformanceCounters table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# AppPerformanceCounters

 Application Insights performance counters.

## Categories

- Applications
## Solutions

- LogManagement
## Resource types

- Application Insights




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AppRoleInstance | string | Role instance of the application. |
| AppRoleName | string | Role name of the application. |
| AppVersion | string | Version of the application. |
| Category | string | Performance counter category. |
| ClientBrowser | string | Browser running on the client device. |
| ClientCity | string | City where the client device is located. |
| ClientCountryOrRegion | string | Country or region where the client device is located. |
| ClientIP | string | IP address of the client device. |
| ClientModel | string | Model of the client device. |
| ClientOS | string | Operating system of the client device. |
| ClientStateOrProvince | string | State or province where the client device is located. |
| ClientType | string | Type of the client device. |
| Counter | string | Performance counter name. |
| IKey | string | Instrumentation key of the Azure resource. |
| Instance | string | Instance identifier, to which the counter is related. |
| Name | string | Performance counter name. |
| OperationId | string | Application-defined operation ID. |
| OperationName | string | Application-defined name of the overall operation. The OperationName values typically match the Name values for AppRequests. |
| ParentId | string | ID of the parent operation. |
| Properties | dynamic | Application-defined properties. |
| ResourceGUID | string | Unique, persistent identifier of an Azure resource. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SDKVersion | string | Version of the SDK used by the application to generate this telemetry item. |
| SessionId | string | Application-defined session ID. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SyntheticSource | string | Synthetic source of the operation. |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when performance counter was recorded. |
| Type | string | The name of the table |
| UserAccountId | string | Application-defined account associated with the user. |
| UserAuthenticatedId | string | Persistent string that uniquely represents each authenticated user in the application. |
| UserId | string | Anonymous ID of a user accessing the application. |
| Value | real | Performance counter value. |
