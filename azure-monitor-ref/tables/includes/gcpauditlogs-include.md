---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: GCPAuditLogs
---


| Column | Type | Description |
|---|---|---|
| AuthenticationInfo | dynamic | Authentication information. |
| AuthorizationInfo | dynamic | Authorization information. If there are multiple resources or permissions involved, then there is one AuthorizationInfo element for each {resource, permission} tuple. |
| _BilledSize | real | The record size in bytes |
| GCPResourceName | string | The resource or collection that is the target of the operation. The name is a scheme-less URI, not including the API service name. |
| GCPResourceType | string | The identifier of the type associated with this resource, such as 'pubsub_subscription'. |
| InsertId | string | Optional. Providing a unique identifier for the log entry allows Logging to remove duplicate entries with the same timestamp and insertId in a single query result. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogName | string | Information including a suffix identifying the log sub-type (e.g., admin activity, system access, data access) and where in the hierarchy the request was made. |
| Metadata | dynamic | Other service-specific data about the request, response, and other information associated with the current audited event. |
| MethodName | string | The name of the service method or operation. For API calls, this should be the name of the API method. |
| NumResponseItems | string | The number of items returned from a list or query API method, if applicable. |
| PrincipalEmail | string | The email address of the authenticated user (or service account on behalf of third party principal) making the request. For third party identity callers, the principalSubject field is populated instead of this field. For privacy reasons, the principal email address is sometimes redacted. |
| ProjectId | string | The identifier of the Google Cloud Platform (GCP) project associated with this resource, such as "my-project". |
| Request | dynamic | The operation request. This may not include all request parameters, such as those that are too large, privacy-sensitive, or duplicated elsewhere in the log record. It should never include user-generated data, such as file contents. When the JSON object represented here has a proto equivalent, the proto name will be indicated in the @type property. |
| RequestMetadata | dynamic | Metadata about the operation. |
| ResourceLocation | dynamic | The resource location information. |
| ResourceOriginalState | dynamic | The resource original state before mutation. Present only for operations which have successfully modified the targeted resource(s). In general, this field should contain all changed fields, except those that are already been included in request, response, metadata or serviceData fields. When the JSON object represented here has a proto equivalent, the proto name will be indicated in the @type property. |
| Response | dynamic | The operation response. This may not include all response elements, such as those that are too large, privacy-sensitive, or duplicated elsewhere in the log record. It should never include user-generated data, such as file contents. When the JSON object represented here has a proto equivalent, the proto name will be indicated in the @type property. |
| ServiceData | dynamic | An object containing fields of an arbitrary type. An additional field "@type" contains a URI identifying the type. Example: { "id": 1234, "@type": "types.example.com/standard/id" }. |
| ServiceName | string | The name of the API service performing the operation. For example, 'compute.googleapis.com'. |
| Severity | string | Optional. The severity of the log entry. For example, the following filter expression will match log entries with severities INFO, NOTICE, and WARNING. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | dynamic | The status of the overall operation. |
| StatusMessage | string | The message status of the overall operation. |
| Subscription | string | A named resource representing the stream of messages from a single, specific topic, to be delivered to the subscribing application. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time the log entry was received by logging. |
| Timestamp | datetime | The time the event described by the log entry occurred. |
| Type | string | The name of the table |
