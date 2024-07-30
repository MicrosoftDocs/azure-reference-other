---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: MADeviceNotEnrolled
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ConfigMgrClientID | string |   |
| ConfigMgrLastSeenDate | datetime |   |
| DeviceName | string |   |
| HasEnrollmentError | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OEMSerialNumber | string |   |
| PropertyBag | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
