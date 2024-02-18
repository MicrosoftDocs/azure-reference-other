---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Windows365AuditLogs
---


| Column | Type | Description |
|---|---|---|
| ActivityId | string | The activity Id of the operation. |
| ApplicationId | string | The caller application id of the operation. |
| ApplicationName | string | The application name of the operation. |
| _BilledSize | real | The record size in bytes |
| BuildVersion | string | The build version of the operation. |
| CallerExtendedProperties | string | The caller extended properties of the operation. |
| ComponentName | string | The component name of the operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The name of the operation. |
| OtherAuditEventProperties | string | The audit event properties of the operation, include componentName, operationType, category, activityDateTime, auditEventId, correlationId, shoeboxCategory, and resources. |
| OtherIdentityProperties | string | The identity properties of the user, include Type, UserPermission, ApplicationDisplayName, ServicePrincipleName, UserScopeTags, RemoteTenantId, and RemoteUserId. |
| Pid | string | The pid of the operation. |
| RelatedActivityId | string | The related activity Id of the operation. |
| ResourceExtendedProperties | string | The resource extended properties of the operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Result | string | The result of the operation. |
| ScenarioId | string | The scenario Id of the operation. |
| ScenarioInstanceId | string | The scenario instance Id of the operation. |
| ServiceName | string | The service name of the operation. |
| SessionId | string | The session Id of the operation. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| Tid | string | The tid of the operation. |
| TimeGenerated | datetime | Date and time when the report was generated (UTC). |
| Type | string | The name of the table |
| UserId | string | The user Id of the user. |
| UserPrincipalName | string | The user principal name of the user. |
