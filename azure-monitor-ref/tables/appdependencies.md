---
title: Azure Monitor Logs reference - AppDependencies
description: Reference for AppDependencies table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# AppDependencies

 Application Insights dependencies.

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
| ClientBrowser | string | Browser running on the client device. |
| ClientCity | string | City where the client device is located. |
| ClientCountryOrRegion | string | Country or region where the client device is located. |
| ClientIP | string | IP address of the client device. |
| ClientModel | string | Model of the client device. |
| ClientOS | string | Operating system of the client device. |
| ClientStateOrProvince | string | State or province where the client device is located. |
| ClientType | string | Type of the client device. |
| Data | string | Detailed information about the dependency call, such as a full URI or a SQL statement. |
| DependencyType | string | Dependency type, such as HTTP or SQL. |
| DurationMs | real | Number of milliseconds the dependency call took to complete. |
| Id | string | Application-generated, unique ID of the dependency call. |
| IKey | string | Instrumentation key of the Azure resource. |
| ItemCount | int | Number of telemetry items represented by a single sample item. |
| Measurements | dynamic | Application-defined measurements. |
| Name | string | Dependency name, such as an URI query without parameters or a SQL server table name. |
| OperationId | string | Application-defined operation ID. |
| OperationName | string | Application-defined name of the overall operation. The OperationName values typically match the Name values for AppRequests. |
| ParentId | string | ID of the parent operation. |
| Properties | dynamic | Application-defined properties. |
| ReferencedItemId | string | Id of the item with additional details about the dependency call. |
| ReferencedType | string | Name of the table with additional details about the dependency call. |
| ResourceGUID | string | Unique, persistent identifier of an Azure resource. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultCode | string | Result code returned to the application by the dependency call. |
| SDKVersion | string | Version of the SDK used by the application to generate this telemetry item. |
| SessionId | string | Application-defined session ID. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Success | bool | Indicates whether the dependency call completed successfully. |
| SyntheticSource | string | Synthetic source of the operation. |
| Target | string | Target of a dependency call, such as a Web or a SQL server name. |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when dependency call was recorded. |
| Type | string | The name of the table |
| UserAccountId | string | Application-defined account associated with the user. |
| UserAuthenticatedId | string | Persistent string that uniquely represents each authenticated user in the application. |
| UserId | string | Anonymous ID of a user accessing the application. |
