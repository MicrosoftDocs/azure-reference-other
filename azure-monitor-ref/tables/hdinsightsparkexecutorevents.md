---
title: Azure Monitor Logs reference - HDInsightSparkExecutorEvents
description: Reference for HDInsightSparkExecutorEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# HDInsightSparkExecutorEvents

 Spark Executor Events.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AddedTime | datetime | The time (UTC) the Executor was added. |
| ApplicationId | string | The application ID of the application producing the record. |
| _BilledSize | real |  |
| ClusterDnsName | string | The DNS name of the cluster running the Executor. |
| ClusterTenantId | string | The tenant ID of the cluster running the Executor. |
| ExecutorCores | int | The number of cores the Spark Executor has. |
| ExecutorHost | string | The host the Executor ran on |
| ExecutorId | string | The ID of the Spark Executor. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node running the Executor. |
| _IsBillable | string |  |
| Region | string | The region of the cluster running the Executor. |
| RemovedReason | string | The reason the Executor was removed. |
| RemovedTime | datetime | The time (UTC) the Executor was removed. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node  running the Executor. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the Executor. |
