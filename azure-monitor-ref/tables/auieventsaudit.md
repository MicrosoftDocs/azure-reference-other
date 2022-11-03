---
title: Azure Monitor Logs reference - AUIEventsAudit
description: Reference for AUIEventsAudit table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# AUIEventsAudit

 All API requests in the context of the Customer Insights (AUI) instance, for example all user actions while configuring and using the instance. POST|PUT|DELETE|PATCH operations go into this category.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Audience | string | The audience for which the accessToken was requested for. |
| CallerIPAddress | string | Caller IP address, if the operation corresponds to an API call that would come from an entity with a publicly available IP address. |
| CallerObjectId | string | Azure Active Directory ObjectId of the caller. |
| Category | string | Log category of the event. Either Operational or Audit. All POST/PUT/PATCH/DELETE HTTP Requests are tagged with Audit, everything else with Operational. |
| Claims | string | Claims of the user or app JSON web token (JWT). Claim properties vary per organization and the Azure Active Directory configuration. |
| CorrelationId | string | The ID for the correlated events. Can be used to identify correlated events between multiple tables. |
| DurationMs | long | Duration of the operation in milliseconds. |
| EventType | string | Always ApiEvent, marking the log event as API event. |
| InstanceId | string | Customer Insights (AUI) instanceId. |
| Level | string | Severity level of the event, is one of: Informational, Warning, Error, or Critical. |
| Method | string | HTTP method: GET/POST/PUT/PATCH/HEAD |
| OperationName | string | Name of the operation represented by this event. |
| OperationStatus | string | Success for HTTP status code < 400, ClientError for HTTP status code < 500, Error for HTTP Status >= 500. |
| Origin | string | URI indicating where a fetch originates from or unknown. |
| Path | string | Relative path of the request. |
| RequiredRoles | string | Required roles to do the operation. Admin role is allowed to do all operations. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string | Sub status of the event. If the operation corresponds to a REST API call, it's the HTTP status code. |
| ResultType | string | Status of the event. Running, Skipped, Successful, Failure. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| Uri | string | Absolute request URI. |
| UserAgent | string | Browser agent sending the request or unknown. |
| UserPrincipalName | string | The UserPrincipalName is the Azure AD username for the user accounts. |
| UserRole | string | Assigned role for the user or app. |
