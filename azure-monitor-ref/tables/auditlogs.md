---
title: Azure Monitor Logs reference - AuditLogs
description: Reference for AuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# AuditLogs

 Audit log for Azure Active Directory. Includes system activity information about user and group management managed applications and directory activities.

## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime|Date and time the record was created.|
|ResourceId|string||
|OperationName|string|Name of the operation.|
|OperationVersion|string|REST API version that's requested by the client.|
|Category|string|Currently Audit is the only supported value.|
|ResultType|string|Result of the operation. Possible values are Success and Failure.|
|ResultSignature|string|Property is not used and can be ignored.|
|ResultDescription|string|Additional description of the result.|
|DurationMs|long|Property is not used and can be ignored.|
|CorrelationId|string|Optional GUID that's passed by the client. Can help correlate client-side operations with server-side operations and is useful when tracking logs that span services.|
|Resource|string||
|ResourceGroup|string||
|ResourceProvider|string||
|Identity|string|Identity from the token that was presented when the request was made. The identity can be a user account system account or service principal.|
|Level|string|Message type. This is currently always Informational.|
|Location|string|Location of the datacenter.|
|AdditionalDetails|dynamic|Indicates additional details on the activity.|
|Id|string|GUID that uniquely identifies the activity.|
|InitiatedBy|dynamic|User or app initiated the activity.|
|LoggedByService|string|Service that initiated the activity (For example: Self-service Password Management Core Directory B2C Invited Users Microsoft Identity Manager Privileged Identity Management.|
|Result|string|Result of the activity. Possible values are: success failure timeout unknownFutureValue.|
|ResultReason|string|Describes cause of failure or timeout results.|
|TargetResources|dynamic|Indicates information on which resource was changed due to the activity. Target Resource Type can be User Device Directory App Role Group Policy or Other.|
|AADTenantId|string|ID of the ADD tenant|
|ActivityDisplayName|string|Activity name or the operation name. Examples include Create User and Add member to group. For full list see Azure AD activity list.|
|ActivityDateTime|datetime|Date and time the activity was performed in UTC.|
|AADOperationType|string|Type of the operation. Possible values are Add Update Delete and Other.|
|Type|string||
