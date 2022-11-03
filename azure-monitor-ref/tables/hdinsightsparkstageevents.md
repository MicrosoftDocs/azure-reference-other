---
title: Azure Monitor Logs reference - HDInsightSparkStageEvents
description: Reference for HDInsightSparkStageEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# HDInsightSparkStageEvents

 Spark Stage Events.

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
| AttemptId | string | The Id of the stage attempt. |
| ClusterDnsName | string | The DNS name of the cluster running the stage. |
| ClusterTenantId | string | The tenant ID of the cluster running the stage. |
| CompletionTime | datetime | The time (UTC) the stage was completed. |
| Details | string | The exception details for any stage failures. |
| FailureReason | string | The reason for failure if the stage failed. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node running the stage. |
| RDDInfo | string | Json containing information about RDDs used in the stage. |
| Region | string | The region of the cluster running the stage. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node  running the stage. |
| SourceSystem | string |  |
| StageId | string | The ID of the stage. |
| StageName | string | The name of the stage. |
| SubmissionTime | datetime | The time (UTC) the stage was submitted. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TaskCount | int | The count of tasks associated with the stage. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the stage. |
