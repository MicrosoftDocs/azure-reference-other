---
title: Azure Monitor Logs reference - AppMetrics
description: Reference for AppMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# AppMetrics

 Application Insights metrics.

## Categories

- Applications
## Solutions

- LogManagement
## Resource types

- Application Insights




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|TimeGenerated|datetime|Date and time when metric was generated.|
|Name|string|Application-defined name|
|ItemCount|int|The number of measurements that were aggregated into trackMetric(..) call.|
|Sum|real|This is the sum of the measurements. To get the mean value, divide by valueCount.|
|Min|real|The minimum value in the measurements that were aggregated into trackMetric(..) call.|
|Max|real|The maximum value in the measurements that were aggregated into trackMetric(..) call.|
|Properties|dynamic|Application-defined properties.|
|OperationName|string|Application-defined name of the overall operation. The OperationName values typically match the Name values for AppRequests.|
|OperationId|string|Application-defined operation ID.|
|ParentId|string|ID of the parent operation.|
|SyntheticSource|string|Synthetic source of the operation.|
|SessionId|string|Application-defined session ID.|
|UserId|string|Anonymous ID of a user accessing the application.|
|UserAuthenticatedId|string|Persistent string that uniquely represents each authenticated user in the application.|
|UserAccountId|string|Application-defined account associated with the user.|
|AppVersion|string|Version of the application.|
|AppRoleName|string|Role name of the application.|
|AppRoleInstance|string|Role instance of the application.|
|ClientType|string|Type of the client device.|
|ClientModel|string|Model of the client device.|
|ClientOS|string|Operating system of the client device.|
|ClientIP|string|IP address of the client device.|
|ClientCity|string|City where the client device is located.|
|ClientStateOrProvince|string|State or province where the client device is located.|
|ClientCountryOrRegion|string|Country or region where the client device is located.|
|ClientBrowser|string|Browser running on the client device.|
|ResourceGUID|string|Unique, persistent identifier of an Azure resource.|
|IKey|string|Instrumentation key of the Azure resource.|
|SDKVersion|string|Version of the SDK used by the application to generate this telemetry item.|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
