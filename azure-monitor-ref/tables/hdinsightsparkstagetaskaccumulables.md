---
title: Azure Monitor Logs reference - HDInsightSparkStageTaskAccumulables
description: Reference for HDInsightSparkStageTaskAccumulables table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
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
| ClusterDnsName | string | The DNS name of the cluster where the metric was collected. |
| ClusterTenantId | string | The tenant ID of the cluster where the metric was collected. |
| Entity | string | The name of the entity being described. |
| EntityId | string | The ID of the entity. |
| Host | string | The FQDN of the host where the metric was collected. |
| IpAddress | string | The IP Address of the node where the metric was collected. |
| MetricId | string | The ID of the metric. |
| MetricName | string | The name of the metric. |
| MetricValue | long | The value of the metric. |
| ParentId | string | The ID of the parent entity. |
| Region | string | The region of the cluster where the metric was collected. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node where the metric was collected. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster where the metric was collected. |
