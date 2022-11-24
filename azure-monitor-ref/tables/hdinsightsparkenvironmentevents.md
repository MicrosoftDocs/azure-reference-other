---
title: Azure Monitor Logs reference - HDInsightSparkEnvironmentEvents
description: Reference for HDInsightSparkEnvironmentEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# HDInsightSparkEnvironmentEvents

 Spark Environment Events.

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
| ClusterDnsName | string | The DNS name of the cluster running the application. |
| ClusterTenantId | string | The tenant ID of the cluster running the application. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node running the application. |
| Region | string | The region of the cluster running the application. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node running the application. |
| SourceSystem | string |  |
| SparkDeployMode | string | The spark deployment mode of the application. |
| SparkExecutorCores | int | The number of Executor cores. |
| SparkExecutorInstances | int | The number of Spark Executor instances. |
| SparkExecutorMemory | string | The memory usage of the Spark Executor |
| SparkMaster | string | The master mode of the Spark Application |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the application |
| YarnMaxAttempts | int | The max number of attempts Yarn will make for the application. |
| YarnQueue | string | The type of YARN queue for the application. |
| YarnTags | string | The YARN tag of the application. |
