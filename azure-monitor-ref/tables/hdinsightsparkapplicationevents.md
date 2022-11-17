---
title: Azure Monitor Logs reference - HDInsightSparkApplicationEvents
description: Reference for HDInsightSparkApplicationEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# HDInsightSparkApplicationEvents

 Spark Application Events.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AppAttemptId | string | The application attempt id. |
| ApplicationId | string | The application id of the application producing the record. |
| AppName | string | The application name. |
| ClusterDnsName | string | The DNS name of the cluster running the application. |
| ClusterTenantId | string | The tenant ID of the cluster running the application. |
| CompletionTime | datetime | The time (UTC) the application submission completed. |
| Host | string | The fqdn the node was run on. |
| IpAddress | string | The IP Address of the node running the application. |
| Region | string | The region of the cluster running the application. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node running the application. |
| SourceSystem | string |  |
| SparkUser | string | The Spark User associated with the record. |
| SubmissionTime | datetime | The time (UTC) the application was submitted. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the application |
