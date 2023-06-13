---
title: Azure Monitor Logs reference - HDInsightHiveAndLLAPLogs
description: Reference for HDInsightHiveAndLLAPLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# HDInsightHiveAndLLAPLogs

 All logs from HDInsight Hive and LLAP Clusters.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| ClusterName | string | Name of cluster. |
| ClusterType | string | Type of the cluster. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| HostName | string | Name of host where log was emitted. |
| _IsBillable | string |  |
| LogLevel | string | log level of message (INFO, WARN, ERROR, etc.). |
| LogType | string | The name of the log file that a record came from (e.g. HiveServerLog, WebHCatLog, etc.). |
| Message | string | message from Hive or LLAP log. |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
