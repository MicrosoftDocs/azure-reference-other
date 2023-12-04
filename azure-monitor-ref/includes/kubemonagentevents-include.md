---
ms.service: azure-monitor
ms.topic: include
ms.date: 12/04/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: KubeMonAgentEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | Category of the event. For example: container.azm.ms/promscraping, container.azm.ms/configmap. |
| ClusterId | string | ID of the kubernetes cluster from which the event was sourced |
| ClusterName | string | ID of the kubernetes cluster from which the event was sourced |
| Computer | string | Computer/node name in the cluster for which the event applies. If not, computer/node name of sourcing computer |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | Event level for the event. [Error, Warning, Info] |
| Message | string | Event message. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string | Dimensions/properties for the event |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
