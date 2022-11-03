---
title: Azure Monitor Logs reference - HDInsightHiveTezAppStats
description: Reference for HDInsightHiveTezAppStats table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# HDInsightHiveTezAppStats

 Tez Application Metrics emitted from the YARN Resource Manager.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AMContainerLogs | string | The Application Master? container logs. |
| ApplicationId | string | The ID of the Application that the metrics describe. |
| ApplicationName | string | The name of the application that the metrics describe. |
| ApplicationType | string | The type of application. |
| ClusterId | long | The final status of the application if it has reached a terminal state. |
| ClusterName | string | Name of cluster. |
| ClusterType | string | Name of cluster. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| ElapsedTime | long | The time elapsed while the application was running. |
| FinalStatus | string | The final status of the application if it has reached a terminal state. |
| FinishedTime | long | The time the application finished. |
| HostName | string | Name of host where log was emitted. |
| LogAggregationStatus | string | The log aggregation status. |
| MetricName | string | Name of the metric for the record (e.g. AppsCompleted, AppsKilled, AppsFailed , etc). |
| MetricValue | real | Value of metric in the record. |
| OperationName | string | The operation associated with log record. |
| Queue | string | The queue of the application. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| StartedTime | long | The time the application started. |
| State | string | The state of the application. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | dynamic | Information about the record. For example a record may be tagged with 'yarn' if it is in the yarn context. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TrackingUI | string | ?. |
| Type | string | The name of the table |
| UnmanagedApplication | bool | True if application is unmanaged, false if otherwise. |
| User | string | The name of the user of the application. |
