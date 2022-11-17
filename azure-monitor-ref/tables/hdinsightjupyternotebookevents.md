---
title: Azure Monitor Logs reference - HDInsightJupyterNotebookEvents
description: Reference for HDInsightJupyterNotebookEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# HDInsightJupyterNotebookEvents

 Spark Events Log.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClusterDnsName | string | The DNS name of the cluster running the application. |
| ClusterTenantId | string | The tenant ID of the cluster running the application. |
| Dim0 | string | Varies based of of type of event. |
| Dim1 | datetime | Varies based of of type of event. |
| Dim10 | string | Varies based of of type of event. |
| Dim2 | int | Varies based of of type of event. |
| Dim3 | int | Varies based of of type of event. |
| Dim4 | string | Varies based of of type of event. |
| Dim5 | int | Varies based of of type of event. |
| Dim6 | string | Varies based of of type of event. |
| Dim7 | string | Varies based of of type of event. |
| Dim8 | string | Varies based of of type of event. |
| Dim9 | string | Varies based of of type of event. |
| EventName | string | The name of the event. |
| Host | string | The FQDN of the host. |
| IpAddress | string | The IP Address of the node running the application. |
| Region | string | The region of the cluster running the application. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node the application running the application. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the application |
