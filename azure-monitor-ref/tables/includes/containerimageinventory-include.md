---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ContainerImageInventory
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string | Computer name/Node name |
| Failed | int | Count of containers with this image that are in failed state |
| Image | string | Name of Container Image |
| ImageID | string | Image ID of the container image |
| ImageSize | string | Size of the container image [amount of data (on disk) that is used for the writable layer] |
| ImageTag | string | Tag of the container image |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Paused | int | Count of containers with this image that are in paused state |
| Repository | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Running | int | Count of containers with this image that are in running state |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Stopped | int | Count of containers with this image that are in stopped state |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| TotalContainer | long | Count of containers with this ContainerImage |
| Type | string | The name of the table |
| VirtualSize | string | Virtual Size of the Container Image [Total amount of disk-space used for the read-only image data] |
