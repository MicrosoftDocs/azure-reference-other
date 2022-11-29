---
title: Azure Monitor Logs reference - AUIEventsOperational
description: Reference for AUIEventsOperational table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# AUIEventsOperational

 Events generated using the service, for example GET requests or the execution events of a workflow.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AdditionalInformation | string | Contains AffectedEntities, MessageCode and entityCount. |
| Audience | string | The audience for which the accessToken was requested for. |
| CallerIPAddress | string | Caller IP address, if the operation corresponds to an API call that would come from an entity with a publicly available IP address. |
| CallerObjectId | string | Azure Active Directory ObjectId of the caller. |
| Category | string | Log category of the event. Either Operational or Audit. All POST/PUT/PATCH/DELETE HTTP Requests are tagged with Audit, everything else with Operational. |
| Claims | string | Claims of the user or app JSON web token (JWT). Claim properties vary per organization and the Azure Active Directory configuration. |
| CorrelationId | string | The ID for the correlated events. Can be used to identify correlated events between multiple tables. |
| DurationMs | long | Duration of the operation in milliseconds. |
| EndTime | datetime | Specifies the date and time that the workflow job ended (UTC) |
| Error | string | Error Message with more details. |
| EventType | string | The type of the event. Either ApiEvent or WorkflowEvent |
| FriendlyName | string | User friendly Name of the Export or the Entity which is processed. |
| Identifier | string | Depending on the OperationType in can be: the guid of the export configuration, the guid of the Enrichment, the Entity Name. |
| InstanceId | string | Customer Insights (AUI) instance ID. |
| Level | string | Severity level of the event, is one of: Informational, Warning or Error. |
| Method | string | HTTP method: GET/POST/PUT/PATCH/HEAD |
| OperationName | string | Name of the operation represented by this event. {OperationType}.[WorkFlow\|Task][Started\|Completed]. |
| OperationStatus | string | Success for HTTP Status code < 400, ClientError for HTTP Status code < 500, Error for HTTP Status >= 500. |
| OperationType | string | Identifier of the operation. |
| Origin | string | URI indicating where a fetch originates from or unknown. |
| Path | string | Relative path of the request. |
| RequiredRoles | string | Required roles to do the operation. Admin role is allowed to do all operations. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string | Sub status of the event. If the operation corresponds to a REST API call, it's the HTTP status code. |
| ResultType | string | Status of the event. Running, Skipped, Successful, Failure. |
| SourceSystem | string |  |
| StartTime | datetime | Specifies the date and time that the workflow job was started (UTC) |
| SubmittedBy | string | Workflow events only. The Azure Active Directory objectId of the user who triggered the workflow, see also properties.workflowSubmissionKinds. |
| SubmittedTime | datetime | Specifies the date and time that the workflow job was submitted (UTC) |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TasksCount | int | Workflow only. Number of tasks the Workflow triggers. |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp of the event (UTC). |
| Type | string | The name of the table |
| Uri | string | Absolute request URI. |
| UserAgent | string | Browser agent sending the request or unknown. |
| UserPrincipalName | string | The UserPrincipalName is the Azure AD username for the user accounts. |
| UserRole | string | Assigned role for the user or app. |
| WorkflowJobId | string | Identifier of the workflow run. All Workflow and Tasks events within the workflow execution have the same workflowJobId. |
| WorkflowStatus | string | Running, Successful. |
| WorkflowSubmissionKind | string | OnDemand or Scheduled. |
| WorkflowType | string | Full or incremental refresh. |
