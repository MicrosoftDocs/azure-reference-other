---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: KubePodInventory
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClusterId | string | ID of the kubernetes cluster from which the event was sourced |
| ClusterName | string | ID of the kubernetes cluster from which the event was sourced |
| Computer | string | Computer/node name in the cluster that has this pod/container. Unscheduled pods will have this as empty. |
| ContainerCreationTimeStamp | datetime | Container creation time |
| ContainerID | string | Container's ID |
| ContainerLastStatus | string | Container's last observed last status |
| ContainerName | string | Container name. This is in poduid/containername format. |
| ContainerRestartCount | int | Restart count for the container |
| ContainerStartTime | datetime | Time container started. |
| ContainerStatus | string | Container's last observered current state [container.state] |
| ContainerStatusReason | string | Reason if any for container's status. |
| ControllerKind | string | Container/Pod's controller kind. For example: ReplicaSet  |
| ControllerName | string | Container/Pod's controller Name. Ex;- kubernetes-dashboard-9f5bf9974  |
| InstanceName | string | Not used currently[for future use] |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Name | string | Kubernetes Pod Name |
| Namespace | string | Kubernetes Namespace for the pod/container |
| PodCreationTimeStamp | datetime | Pod creation time |
| PodIp | string | Pod's IP Address |
| PodLabel | string | Pod Labels |
| PodRestartCount | int | Restart count for the pod. [Sum of all restarts of all containers in the pod] |
| PodStartTime | datetime | Pod's start time (for started pods) |
| PodStatus | string | Last observed Pod Status [pod.status.phase] |
| PodUid | string | Unique ID of the pod |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ServiceName | string | Kubernetes Service the pod belongs to (if any) |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
