---
title: Azure Monitor Logs reference - AppCenterError
description: Reference for AppCenterError table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AppCenterError

 

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Annotation | string |  |
| _BilledSize | real |  |
| CreatedAt | datetime |  |
| ErrorClass | string |  |
| ErrorFile | string |  |
| ErrorGroupId | string |  |
| ErrorId | string |  |
| ErrorLine | int |  |
| ErrorMethod | string |  |
| ErrorReason | string |  |
| ErrorType | string |  |
| ExceptionType | string |  |
| _IsBillable | string |  |
| JailBreak | bool |  |
| LastErrorAt | datetime |  |
| Model | string |  |
| Oem | string |  |
| OsVersion | string |  |
| SchemaType | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| Status | string |  |
| SymbolicatedAt | datetime |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UserString | string |  |
