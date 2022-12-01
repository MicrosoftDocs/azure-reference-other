---
title: Azure Monitor Logs reference - HDInsightSparkSQLExecutionEvents
description: Reference for HDInsightSparkSQLExecutionEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# HDInsightSparkSQLExecutionEvents

 Spark SQL Execution Events.

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
| ClusterDnsName | string | The DNS name of the cluster running the Spark SQL execution. |
| ClusterTenantId | string | The tenant ID of the cluster running the Spark SQL execution. |
| EndTime | datetime | The time (UTC) the Spark SQL execution ended. |
| ExecutionId | string | The ID of the Spark SQL execution. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node running the Spark SQL execution. |
| PhysicalPlanDescription | string | The description of the Physical/Logical plan of the Spark SQL execution. |
| Region | string | The region of the cluster running the Spark SQL execution. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node  running the Spark SQL execution. |
| SourceSystem | string |  |
| SparkPlanInfo | string | Json object containing information on the Spark SQL execution. |
| StartTime | datetime | The time (UTC) the Spark SQL execution started. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the Spark SQL execution. |
