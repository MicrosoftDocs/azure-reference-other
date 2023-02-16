---
title: Azure Monitor Logs reference - AzureDevOpsAuditing
description: Reference for AzureDevOpsAuditing table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/16/2023
---

# AzureDevOpsAuditing

 Schema for Azure DevOps audit logs, which can be used to track the many changes that occur within your Azure DevOps organization(s). Some examples include changes to security policies, pipelines, billing, and projects. For a full list of events, see aka.ms/azdev-audit-events.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityId | string | Unique identifier for the action that occurred. |
| ActorClientId | string | When the action was performed by a managed identity or other service principal, this value represents the client ID of that principal. Otherwise, this value is 00000000-0000-0000-0000-000000000000. When this field is populated, ActorCUID and ActorUserId will both be 00000000-0000-0000-0000-000000000000. |
| ActorCUID | string | When the action was performed by a user, this value represents a consistently unique identifier for that actor. Otherwise, this value is 00000000-0000-0000-0000-000000000000. When this field, along with ActorUserId, is populated, ActorClientId will be 00000000-0000-0000-0000-000000000000. |
| ActorDisplayName | string | Display name of the user who initiated the auditing event to be logged. |
| ActorUPN | string | The actor's user principal name. |
| ActorUserId | string | When the action was performed by a user or Azure DevOps service, this value represents that actor's user identifier. Otherwise, this value is 00000000-0000-0000-0000-000000000000. When this field, along with ActorUserId, is populated, ActorClientId will be 00000000-0000-0000-0000-000000000000. |
| Area | string | Part of the Azure DevOps product where the auditing event occurred. |
| AuthenticationMechanism | string | Type of authentication used by the actor. |
| Category | string | Type of action that occurred when the auditing event was logged. |
| CategoryDisplayName | string | Type of action that occurred when the auditing event was logged. |
| CorrelationId | string | CorrelationId allows two or more auditing events to be grouped together. This happens when a single action causes a cascade of auditing entries. An example being project creation. |
| Data | dynamic | Additional data that's unique to the type of auditing event. |
| Details | string | Description of what happened. |
| Id | string | The identifier for the audit event, unique across services. |
| IpAddress | string | IP address where the event originated. |
| OperationName | string | The unique identifier for the type of auditing event that occurred. For example, Git.CreateRepo identifies the an auditing event for Git repository creation. |
| ProjectId | string | Unique identifier of the project that an auditing event occurred in. If not provided then the event isn't scoped to a particular project. |
| ProjectName | string | Friendly name of the project that an auditing event occurred in. If not provided then the event isn't scoped to a particular project. |
| ScopeDisplayName | string | User friendly name for the scope level that an auditing event occurred at. |
| ScopeId | string | The organization identifier. |
| ScopeType | string | The level (scope) that the event occurred. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | The time the auditing event occurred in UTC. |
| Type | string | The name of the table |
| UserAgent | string | The user agent from the request. |
