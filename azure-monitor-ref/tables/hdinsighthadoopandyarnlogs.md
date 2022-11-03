---
title: Azure Monitor Logs reference - HDInsightHadoopAndYarnLogs
description: Reference for HDInsightHadoopAndYarnLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# HDInsightHadoopAndYarnLogs

 Logs from HDInsight Hadoop Clusters and YARN-related logs such as ResourceManager, NodeManager, and TimelineServer logs from all cluster types that use YARN.

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
| ClusterType | string | Type of the cluster. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| HostName | string | Name of host where log was emitted. |
| LogLevel | string | log level of message (INFO, WARN, ERROR, etc.). |
| LogType | string | The name of the log file that a record came from (e.g. YarnTimeLineServer, YarnResourceManager, etc.). |
| Message | string | message from Hadoop or YARN log. |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
