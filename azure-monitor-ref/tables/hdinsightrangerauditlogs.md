---
title: Azure Monitor Logs reference - HDInsightRangerAuditLogs
description: Reference for HDInsightRangerAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# HDInsightRangerAuditLogs

 Audit logs from the Ranger component (only for ESP clusters).

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccessName | string | Name of the access method. |
| Action | string | Type of action made by the event. |
| AdditionalInfo | string | Additional info about the request including the remote and forwarded IPs |
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
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string | List of tags associated with the event. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
