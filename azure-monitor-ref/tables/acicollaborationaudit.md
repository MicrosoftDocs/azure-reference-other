---
title: Azure Monitor Logs reference - ACICollaborationAudit
description: Reference for ACICollaborationAudit table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# ACICollaborationAudit

 Audits of collaborative resources approval and access during pipeline execution.

## Categories

- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Project CI Workspace




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CorrelationId | string | The ID for correlated pipeline run events. Can be used to identify audits that belong to the same pipeline run. |
| EntitlementResult | string | The result of the entitlement evaluation. Options are: Granted = access granted; Denied = access was not granted; Revoked = accessed was revoked because the pipeline could not be fully approved; Actualized = the resource was accessed by the pipeline run. |
| EntitlementSummary | string | Textual summary of the granted access. |
| GrantCorrelationId | string | The ID for the grant events. Can be used to correlate between different results of the same grant. |
| GrantSource | string | The azure resource ID of the resource the grant is based on. |
| GrantSourceType | string | The type of the the resource the grant is based on. |
| GrantType | string | The method used to grant access to the resource (Owned, Reference, Entitlement). |
| Location | string | The Location (Region) the resource was accessed in. |
| OperationName | string | The operation associated with audit record. |
| ParticipantName | string | The participant friendly name as used in the contract negotiation. |
| ParticipantTenantId | string | The participant tenant id. Enable query by the granted tenant invariant id. Example of retrieving this is for contoso: https://login.microsoftonline.com/contoso.com/.well-known/openid-configuration |
| ReferencedResourceId | string | The storage resource that the accessed CI resource points to, if applicable |
| ReferencedResourceType | string | The storage resource type that the accessed CI resource points to, if applicable. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetResourceId | string | The azure resource ID of the accessed resource. |
| TargetResourceType | string | The resource type of the accessed resource. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the audit was generated. |
| Type | string | The name of the table |
| UserName | string | Name of the user that initiated the pipeline. Available only if the audit relate to owned resource |
