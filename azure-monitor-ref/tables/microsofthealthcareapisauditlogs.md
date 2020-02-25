---
title: Azure Monitor Logs reference - MicrosoftHealthcareApisAuditLogs
description: Reference for MicrosoftHealthcareApisAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# MicrosoftHealthcareApisAuditLogs

 Azure API for FHIR audit logs

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log.|
|OperationName|string|The name of the operation represented by this event.|
|CorrelationId|string|The correlation id of the request.|
|RequestUri|string|The URI of the request.|
|FhirResourceType|string|The resource type the operation was executed for.|
|StatusCode|int|The HTTP status code.|
|ResultType|string|The result type.|
|OperationDuration|int|The duration of the operation in ms.|
|LogCategory|string|The audit event category.|
|CallerIPAddress|string|The IP address of the caller.|
|CallerIdentityIssuer|string|The JWD token Issuer.|
|CallerIdentityObjectId|string|The AAD object ID.|
|CallerIdentity|dynamic|The caller's identity.|
|Location|string|The location of the server that processed the request (e.g., South Central US).|
|Properties|dynamic|Additional properties.|
|Type|string||
|_ResourceId|string||
