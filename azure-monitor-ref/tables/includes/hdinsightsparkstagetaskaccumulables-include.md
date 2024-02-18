---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HDInsightSparkStageTaskAccumulables
---


| Column | Type | Description |
|---|---|---|
| ApplicationId | string | The application ID of the application producing the record. |
| _BilledSize | real | The record size in bytes |
| ClusterDnsName | string | The DNS name of the cluster where the metric was collected. |
| ClusterTenantId | string | The tenant ID of the cluster where the metric was collected. |
| Entity | string | The name of the entity being described. |
| EntityId | string | The ID of the entity. |
| Host | string | The FQDN of the host where the metric was collected. |
| IpAddress | string | The IP Address of the node where the metric was collected. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MetricId | string | The ID of the metric. |
| MetricName | string | The name of the metric. |
| MetricValue | long | The value of the metric. |
| ParentId | string | The ID of the parent entity. |
| Region | string | The region of the cluster where the metric was collected. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node where the metric was collected. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster where the metric was collected. |
