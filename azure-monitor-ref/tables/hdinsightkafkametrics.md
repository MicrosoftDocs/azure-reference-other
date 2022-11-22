---
title: Azure Monitor Logs reference - HDInsightKafkaMetrics
description: Reference for HDInsightKafkaMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# HDInsightKafkaMetrics

 All metrics from Kafka clusters.

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
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| HostName | string | Name of host where log was emitted. |
| MetricDataType | string | CollectD datatype of the metric (e.g. gauge, counter, etc.). Determines how metric is portrayed over time. Please reference CollectD documentation for more information: https://collectd.org/wiki/index.php/Data_source . |
| MetricName | string | Name of the metric for the record (e.g. OfflinePartitionsCount, UnderReplicatedPartitions, LeaderCount, etc). |
| MetricNamespace | string | Category of metric (e.g. RequestMetrics, BrokerTopicMetrics, KafkaController, etc).  |
| MetricValue | real | Value of metric in the record. |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string | Information about the record. For example a record may be tagged with 'kafka.network' if it is a network related metric. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
