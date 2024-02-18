---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HDInsightRangerAuditLogs
---


| Column | Type | Description |
|---|---|---|
| AccessName | string | Name of the access method. |
| Action | string | Type of action made by the event. |
| AdditionalInfo | string | Additional info about the request including the remote and forwarded IPs |
| _BilledSize | real | The record size in bytes |
| CliIpAddress | string | IP address of where CLI request was made. |
| CliType | string | Type of CLI used to create request. |
| ClusterName | string | Name of cluster. |
| ClusterResource | string | Resource involved in request event. |
| ClusterResourceType | string | The type of resource accessed. |
| ClusterType | string | Type of the cluster that emitted the record. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| Enforcer | string | Name of the policy enforcer. |
| EventCount | int | Number of events associated with the request. |
| EventDurationMs | int | Duration of the event in milliseconds. |
| HostName | string | Name of host where log was emitted. |
| Id | string | ID of the event request. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogType | string | Type of log the record came from. |
| OperationName | string | The operation associated with log record. |
| Policy | int | Code representing the policy. |
| Repo | string | Name the repo. |
| RepoType | int | Integer representing the repo type. |
| RequestData | string | Source that provides the request data. |
| RequestUser | string | Username associated with the event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Result | int | Status code of the event result. |
| SequenceNumber | int | Sequence number of the event. |
| SessionId | string | ID associated witht the user session. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string | List of tags associated with the event. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
