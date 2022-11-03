---
title: Azure Monitor Logs reference - HDInsightHBaseLogs
description: Reference for HDInsightHBaseLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# HDInsightHBaseLogs

 All logs from HDInsight HBase Logs.

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
| ClusterType | string | Name of cluster. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| HostName | string | Name of host where log was emitted. |
| LogLevel | string | log level of message (INFO, WARN, ERROR, etc.). |
| LogType | string | The name of the log file that a record came from (e.g. RegionServer, HMaster). |
| Message | string | message from HBase log. |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
