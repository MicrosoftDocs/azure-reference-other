---
title: Azure Monitor Logs reference - HDInsightKafkaServerLog
description: Reference for HDInsightKafkaServerLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# HDInsightKafkaServerLog

 HDInsight Kafka Server Log

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClusterDnsName | string | Name of cluster |
| ClusterType | string | Type of the Cluster |
| CorrelationId | string | Id of associated events |
| FluentdIngestTimestamp | datetime | Time log was ingested by Fluentd framework |
| HostName | string | Name of host where log was emitted |
| Message | string | Entry of Kafka Server Log |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated |
| Type | string | The name of the table |
