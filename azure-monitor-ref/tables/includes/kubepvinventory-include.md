---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: KubePVInventory
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClusterId | string | The ID of the Kubernetes cluster of the persistent volume |
| ClusterName | string | The name of the Kubernetes cluster of the persistent volume |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| PVAccessModes | string | A comma separated list of access modes of the persistent volume |
| PVCapacityBytes | real | The capacity of the persistent volume measured in bytes |
| PVCName | string | The Kubernetes persistent volume claim name |
| PVCNamespace | string | The Kubernetes namespace of the persistent volume claim |
| PVCreationTimeStamp | datetime | The Kubernetes persistent volume creation time |
| PVName | string | The Kubernetes persistent volume name |
| PVStatus | string | The status of the persistent volume: Available, Bound, Released, or Failed |
| PVStorageClassName | string | The name of the storage class of the persistent volume |
| PVType | string | The type of persistent volume from the list of Kubernetes supported volume plugins |
| PVTypeInfo | dynamic | The specific dimensions relating to the type of the persistent volume |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time the record was created |
| Type | string | The name of the table |
