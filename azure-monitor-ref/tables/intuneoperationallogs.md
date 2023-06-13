---
title: Azure Monitor Logs reference - IntuneOperationalLogs
description: Reference for IntuneOperationalLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# IntuneOperationalLogs

 

## Categories

- IT & Management Tools
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Category | string |  |
| _IsBillable | string |  |
| OperationName | string |  |
| Properties | string |  |
| Result | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
