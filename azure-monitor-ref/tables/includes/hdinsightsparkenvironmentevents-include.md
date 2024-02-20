---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HDInsightSparkEnvironmentEvents
---


| Column | Type | Description |
|---|---|---|
| ApplicationId | string | The application ID of the application producing the record. |
| _BilledSize | real | The record size in bytes |
| ClusterDnsName | string | The DNS name of the cluster running the application. |
| ClusterTenantId | string | The tenant ID of the cluster running the application. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node running the application. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Region | string | The region of the cluster running the application. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node running the application. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SparkDeployMode | string | The spark deployment mode of the application. |
| SparkExecutorCores | int | The number of Executor cores. |
| SparkExecutorInstances | int | The number of Spark Executor instances. |
| SparkExecutorMemory | string | The memory usage of the Spark Executor |
| SparkMaster | string | The master mode of the Spark Application |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the application |
| YarnMaxAttempts | int | The max number of attempts Yarn will make for the application. |
| YarnQueue | string | The type of YARN queue for the application. |
| YarnTags | string | The YARN tag of the application. |
