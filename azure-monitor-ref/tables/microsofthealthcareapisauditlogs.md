---
title: Azure Monitor Logs reference - MicrosoftHealthcareApisAuditLogs
description: Reference for MicrosoftHealthcareApisAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# MicrosoftHealthcareApisAuditLogs

 Azure API for FHIR audit logs

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Azure API for FHIR




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIdentity | dynamic | The caller's identity. |
| CallerIdentityIssuer | string | The JWD token Issuer. |
| CallerIdentityObjectId | string | The AAD object ID. |
| CallerIPAddress | string | The IP address of the caller. |
| CorrelationId | string | The correlation id of the request. |
| FhirResourceType | string | The resource type the operation was executed for. |
| Location | string | The location of the server that processed the request (e.g., South Central US). |
| LogCategory | string | The audit event category. |
| OperationDuration | int | The duration of the operation in ms. |
| OperationName | string | The name of the operation represented by this event. |
| Properties | dynamic | Additional properties. |
| RequestUri | string | The URI of the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The result type. |
| SourceSystem | string |  |
| StatusCode | int | The HTTP status code. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the log. |
| Type | string | The name of the table |
