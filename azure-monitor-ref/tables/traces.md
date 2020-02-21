---
title: Azure Monitor Logs reference - traces
description: Reference for traces table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# traces

 Application Insights Traces Schema

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|TimeGenerated|datetime|Date and time when request was recorded.|
|message|string|The message information.|
|severityLevel|int|The severity level of the message.|
|customDimensions|dynamic|Application-defined dimensions.|
|customMeasurements|dynamic|Application-defined measurements.|
|operation_Name|string|Application-defined operation name.|
|operation_Id|string|Application-defined operation ID.|
|operation_ParentId|string|ID of the parent operation.|
|operation_SyntheticSource|string|Synthetic source of the operation.|
|session_Id|string|Application-defined session ID.|
|user_Id|string|ID of a user accessing the application.|
|user_AuthenticatedId|string|Persistent string that uniquely represents each authenticated user in the application.|
|user_AccountId|string|Application-defined account associated with the user.|
|application_Version|string|Version of the application.|
|client_Type|string|Type of the client device.|
|client_Model|string|Model of the client device.|
|client_OS|string|Operating system of the client device.|
|client_IP|string|IP address of the client device.|
|client_City|string|City where the client device is located.|
|client_StateOrProvince|string|The client state or province.|
|client_CountryOrRegion|string|Country or region where the client device is located.|
|client_Browser|string|Browser running on the client device.|
|cloud_RoleName|string|Role name of the cloud service.|
|cloud_RoleInstance|string|Role instance of the cloud service.|
|appId|string|Unique, persistent identifier of an Application Insights resource.|
|iKey|string|Instrumentation key of the Azure resource.|
|sdkVersion|string|Version of the SDK used by the application.|
|itemId|string|Unique ID of the telemetry item assigned by the Application Insights ingestion endpoint.|
|itemCount|int|Number of telemetry items represented by a single sample item.|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
