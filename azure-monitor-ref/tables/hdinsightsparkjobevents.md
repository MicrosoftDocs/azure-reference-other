---
title: Azure Monitor Logs reference - HDInsightSparkJobEvents
description: Reference for HDInsightSparkJobEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# HDInsightSparkJobEvents

 Spark Job Events.

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
| ClusterDnsName | string | The DNS name of the cluster running the job. |
| ClusterTenantId | string | The tenant  ID of the cluster running the job. |
| CompletionTime | datetime | The time (UTC) the job was completed. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node running the job. |
| JobId | string | The ID of the job. |
| JobResult | string | The result of the job. |
| Region | string | The region of the cluster running the job. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node  running the job. |
| SourceSystem | string |  |
| StageIds | string | The stages included in the job. |
| SubmissionTime | datetime | The time (UTC) the job was submitted. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the job. |
