---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: KubeServices
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClusterId | string | ID of the Kubernetes cluster from which the event was sourced. |
| ClusterIp | string | Cluster IP address of the service. |
| ClusterName | string | Name of the Kubernetes cluster from which the event was sourced. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Namespace | string | Kubernetes namespace for the service. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SelectorLabels | string | Selector labels for label based services. |
| ServiceName | string | Name of the Kubernetes service. |
| ServiceType | string | Type of Kubernetes service [ClusterIP/NodePort/LoadBalancer/ExternalName]. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
