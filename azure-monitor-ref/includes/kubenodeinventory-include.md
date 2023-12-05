---
ms.service: azure-monitor
ms.topic: include
ms.date: 12/04/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: KubeNodeInventory
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClusterId | string | ID of the Kubernetes cluster from which the event was sourced. |
| ClusterName | string | ID of the Kubernetes cluster from which the event was sourced. |
| Computer | string | Computer/node name in the cluster for which the event applies. If not, computer/node name of sourcing computer. |
| CreationTimeStamp | datetime | Node created time. |
| DockerVersion | string | Container runtime version. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| KubeletVersion | string | Version of Kubelet in the node. |
| KubeProxyVersion | string | Version of KubeProxy in the node. |
| KubernetesProviderID | string | Provider ID for Kubernetes. |
| Labels | string | Kubernetes Node Labels. |
| LastTransitionTimeReady | datetime | Last transition to or from ready condition for the node (no matter ready is true/false). |
| OperatingSystem | string | Node's host OS Image. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | Comma separated list of node's status.conditions.type for conditions.status that are true. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
