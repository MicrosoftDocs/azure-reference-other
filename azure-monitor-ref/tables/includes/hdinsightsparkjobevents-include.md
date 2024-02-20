---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HDInsightSparkJobEvents
---


| Column | Type | Description |
|---|---|---|
| ApplicationId | string | The application ID of the application producing the record. |
| _BilledSize | real | The record size in bytes |
| ClusterDnsName | string | The DNS name of the cluster running the job. |
| ClusterTenantId | string | The tenant  ID of the cluster running the job. |
| CompletionTime | datetime | The time (UTC) the job was completed. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node running the job. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| JobId | string | The ID of the job. |
| JobResult | string | The result of the job. |
| Region | string | The region of the cluster running the job. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node  running the job. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StageIds | string | The stages included in the job. |
| SubmissionTime | datetime | The time (UTC) the job was submitted. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the job. |
