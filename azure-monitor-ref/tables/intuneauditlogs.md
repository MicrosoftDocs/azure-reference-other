---
title: Azure Monitor Logs reference - IntuneAuditLogs
description: Reference for IntuneAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# IntuneAuditLogs

 

## Categories

- IT & Management Tools
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Category | string |  |
| CorrelationId | string |  |
| Identity | string |  |
| _IsBillable | string |  |
| OperationName | string |  |
| Properties | string |  |
| ResultDescription | string |  |
| ResultType | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
