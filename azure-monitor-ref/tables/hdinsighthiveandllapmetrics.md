---
title: Azure Monitor Logs reference - HDInsightHiveAndLLAPMetrics
description: Reference for HDInsightHiveAndLLAPMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# HDInsightHiveAndLLAPMetrics

 JMX metrics from Hive and LLAP clusters.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClusterName | string | Name of cluster. |
| ClusterType | string | Type of the cluster. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| HostName | string | Name of host where log was emitted. |
| MetricName | string | Name of the metric for the record (e.g. CacheCapacityRemaining, CacheCapacityRemainingPercentage,CacheCapacityTotal, etc). |
| MetricNamespace | string | Category of metric (value of jmx query string  e.g. Hadoop:service=LlapDaemon,name=LlapDaemonCacheMetrics, etc).  |
| MetricValue | real | Value of metric in the record. |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | dynamic | Information about the record. For example a record may be tagged with 'LlapDaemon' if it came from that process. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
