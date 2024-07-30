---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AppCenterError
---


| Column | Type | Description |
|---|---|---|
| Annotation | string |   |
| _BilledSize | real | The record size in bytes |
| CreatedAt | datetime |   |
| ErrorClass | string |   |
| ErrorFile | string |   |
| ErrorGroupId | string |   |
| ErrorId | string |   |
| ErrorLine | int |   |
| ErrorMethod | string |   |
| ErrorReason | string |   |
| ErrorType | string |   |
| ExceptionType | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| JailBreak | bool |   |
| LastErrorAt | datetime |   |
| Model | string |   |
| Oem | string |   |
| OsVersion | string |   |
| SchemaType | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string |   |
| SymbolicatedAt | datetime |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| UserString | string |   |
