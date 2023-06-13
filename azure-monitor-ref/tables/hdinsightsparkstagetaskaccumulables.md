---
title: Azure Monitor Logs reference - HDInsightSparkStageTaskAccumulables
description: Reference for HDInsightSparkStageTaskAccumulables table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# HDInsightSparkStageTaskAccumulables

 Spark Stage Task Accumulables.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationId | string | The application ID of the application producing the record. |
| _BilledSize | real |  |
| ClusterDnsName | string | The DNS name of the cluster where the metric was collected. |
| ClusterTenantId | string | The tenant ID of the cluster where the metric was collected. |
| Entity | string | The name of the entity being described. |
| EntityId | string | The ID of the entity. |
| Host | string | The FQDN of the host where the metric was collected. |
| IpAddress | string | The IP Address of the node where the metric was collected. |
| _IsBillable | string |  |
| MetricId | string | The ID of the metric. |
| MetricName | string | The name of the metric. |
| MetricValue | long | The value of the metric. |
| ParentId | string | The ID of the parent entity. |
| Region | string | The region of the cluster where the metric was collected. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node where the metric was collected. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster where the metric was collected. |
