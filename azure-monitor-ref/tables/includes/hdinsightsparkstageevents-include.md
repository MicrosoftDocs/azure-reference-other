---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HDInsightSparkStageEvents
---


| Column | Type | Description |
|---|---|---|
| ApplicationId | string | The application ID of the application producing the record. |
| AttemptId | string | The Id of the stage attempt. |
| _BilledSize | real | The record size in bytes |
| ClusterDnsName | string | The DNS name of the cluster running the stage. |
| ClusterTenantId | string | The tenant ID of the cluster running the stage. |
| CompletionTime | datetime | The time (UTC) the stage was completed. |
| Details | string | The exception details for any stage failures. |
| FailureReason | string | The reason for failure if the stage failed. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node running the stage. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| RDDInfo | string | Json containing information about RDDs used in the stage. |
| Region | string | The region of the cluster running the stage. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node  running the stage. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StageId | string | The ID of the stage. |
| StageName | string | The name of the stage. |
| SubmissionTime | datetime | The time (UTC) the stage was submitted. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TaskCount | int | The count of tasks associated with the stage. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the stage. |
