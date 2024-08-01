---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: KubeEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClusterId | string | ID of the kubernetes cluster from which the event was sourced |
| ClusterName | string | ID of the kubernetes cluster from which the event was sourced |
| Computer | string | Computer/node name in the cluster for which the event applies. If not, computer/node name of sourcing computer |
| Count | real | Cumulative count of the number of occurences of a specific event [event.count] . |
| FirstSeen | datetime |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| KubeEventType | string | Type of kubernetes event [event.type]. Ex;- 'Normal'  |
| LastSeen | datetime | Time event was last observed [event.lastTimestamp] |
| Message | string | Event message [event.message] |
| Name | string | Involved kubernetes object's name [event.InvolvedObject.name]. Ex;- 'autoschedulejob-158393400-gkv4g' |
| Namespace | string | Involved kubernetes object's namespace [event.InvolvedObject.namespace]. Ex;- 'kube-system' |
| ObjectKind | string | Kind of kubernetes object applicable for the event [event.InvolvedObject.kind] . Ex;- pod |
| Reason | string | Reason as seen in kubernetes event [event.reason] |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceComponent | string | Source component that generated the event [event.source.component] . Ex;- default-scheduler |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
