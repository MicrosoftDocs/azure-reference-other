---
title: Azure Monitor Logs reference - AppEvents
description: Reference for AppEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# AppEvents

 Application Insights events.

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
|TimeGenerated|datetime|Date and time when customEvent was recorded.|
|Name|string|Human-readable name of the customEvent.|
|Properties|dynamic|Application-defined properties.|
|Measurements|dynamic|Application-defined measurements.|
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
|ItemCount|int|Number of telemetry items represented by a single sample item.|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
