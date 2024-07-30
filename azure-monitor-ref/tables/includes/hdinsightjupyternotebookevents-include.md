---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: HDInsightJupyterNotebookEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
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
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Region | string | The region of the cluster running the application. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | The type of node the application running the application. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserSubscriptionId | string | The subscription ID of the cluster running the application |
