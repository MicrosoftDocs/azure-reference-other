---
title: Azure Monitor Logs reference - HDInsightKafkaServerLog
description: Reference for HDInsightKafkaServerLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# HDInsightKafkaServerLog

 HDInsight Kafka Server Log

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| ClusterDnsName | string | Name of cluster |
| ClusterType | string | Type of the Cluster |
| CorrelationId | string | Id of associated events |
| FluentdIngestTimestamp | datetime | Time log was ingested by Fluentd framework |
| HostName | string | Name of host where log was emitted |
| _IsBillable | string |  |
| Message | string | Entry of Kafka Server Log |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated |
| Type | string | The name of the table |
