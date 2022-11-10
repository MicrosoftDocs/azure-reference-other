---
title: Azure Monitor Logs reference - HDInsightSparkBlockManagerEvents
description: Reference for HDInsightSparkBlockManagerEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# HDInsightSparkBlockManagerEvents

 Spark Block Manager Events.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AddedTime | datetime | The time (UTC) the event was added. |
| ApplicationId | string | The application ID of the application producing the record. |
| BlockHost | string | The block host. |
| BlockManagerHost | string | The host where the Block Manager is running. |
| ClusterDnsName | string | The DNS name of the cluster the Block Manager is running on. |
| ClusterTenantId | string | The tenant ID of the cluster the Block Manager is running on. |
| ExecutorId | string | The ID of the executor running the application. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node the Block Manager is running on. |
| MaxMemory | long | The max memory usage from the event. |
| MaxOffHeapMemory | long | The max off heap memory usage from the event. |
| MaxOnHeapMemory | long | The max on heap memory usage from the event. |
| Region | string | The region of the cluster the Block Manager is running on. |
| RemovedTime | datetime | The time (UTC) the application was removed. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node the Block Manager is running on. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster the Block Manager is running on. |
