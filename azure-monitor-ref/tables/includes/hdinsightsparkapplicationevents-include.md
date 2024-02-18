---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HDInsightSparkApplicationEvents
---


| Column | Type | Description |
|---|---|---|
| AppAttemptId | string | The application attempt id. |
| ApplicationId | string | The application id of the application producing the record. |
| AppName | string | The application name. |
| _BilledSize | real | The record size in bytes |
| ClusterDnsName | string | The DNS name of the cluster running the application. |
| ClusterTenantId | string | The tenant ID of the cluster running the application. |
| CompletionTime | datetime | The time (UTC) the application submission completed. |
| Host | string | The fqdn the node was run on. |
| IpAddress | string | The IP Address of the node running the application. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Region | string | The region of the cluster running the application. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node running the application. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SparkUser | string | The Spark User associated with the record. |
| SubmissionTime | datetime | The time (UTC) the application was submitted. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the application |
