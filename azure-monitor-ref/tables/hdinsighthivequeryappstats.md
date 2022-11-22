---
title: Azure Monitor Logs reference - HDInsightHiveQueryAppStats
description: Reference for HDInsightHiveQueryAppStats table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# HDInsightHiveQueryAppStats

 Hive Query Metrics emitted from the YARN Timeline Server.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClientIpAddress | string | The query client's IP address. |
| ClusterName | string | Name of cluster. |
| ClusterType | string | Type of cluster (e.g. LLAP or Hadoop). |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| Domain | string | The domain associated with the query. |
| Entity | string | Name of the query's entity. |
| EntityType | string | The type of the query's entity. |
| ExecutionMode | string | The execution mode of the query. |
| HiveInstanceType | string | The type of hive instance running the query. |
| HostName | string | Name of host where log was emitted. |
| IsMapReduce | bool | True if the query is a MapReduce query. |
| IsTez | bool | True if the query is a Tez query. |
| MetricName | string | Name of the metric for the record (e.g. AppsCompleted, AppsKilled, AppsFailed , etc). |
| MetricValue | real | Value of metric in the record. |
| OperationName | string | The operation associated with log record. |
| QueryCompletionTime | long | Time that query was completed. |
| QuerySubmissionTime | long | Time that query was submitted. |
| Queue | string | The queue the query was served from. |
| RequestUser | string | The client user that submitted the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SessionId | string | The session ID of the query. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TablesRead | string | The tables read by the query. |
| Tags | dynamic | Information about the record. For example a record may be tagged with 'yarn' if it is in the yarn context. |
| TenantId | string |  |
| ThreadName | string | The name of the thread running the query. |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| User | string | The user of the Hive instance executing the query. |
