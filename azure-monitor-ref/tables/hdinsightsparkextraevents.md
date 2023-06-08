---
title: Azure Monitor Logs reference - HDInsightSparkExtraEvents
description: Reference for HDInsightSparkExtraEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# HDInsightSparkExtraEvents

 Spark Extra Events.

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
| _BilledSize | real |  |
| ClusterDnsName | string | The DNS name of the cluster running the application. |
| ClusterTenantId | string | The tenant  ID of the cluster running the application. |
| EventJson | string | Json with information about the event. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node running the application. |
| _IsBillable | string |  |
| Region | string | The region of the cluster running the application. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node  running the application. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the application. |
