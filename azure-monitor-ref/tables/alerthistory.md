---
title: Azure Monitor Logs reference - AlertHistory
description: Reference for AlertHistory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AlertHistory

 

## Categories

- Azure Monitor
## Solutions

- Alert Management




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AlertContext | string |  |
| AlertDescription | string |  |
| AlertId | string |  |
| AlertName | string |  |
| AlertPriority | string |  |
| AlertSeverity | string |  |
| AlertState | string |  |
| _BilledSize | real |  |
| Custom1 | string |  |
| Custom10 | string |  |
| Custom2 | string |  |
| Custom3 | string |  |
| Custom4 | string |  |
| Custom5 | string |  |
| Custom6 | string |  |
| Custom7 | string |  |
| Custom8 | string |  |
| Custom9 | string |  |
| _IsBillable | string |  |
| LastModifiedBy | string |  |
| ManagementGroupName | string |  |
| RepeatCount | int |  |
| ResolvedBy | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceDisplayName | string |  |
| SourceFullName | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TicketId | string |  |
| TimeGenerated | datetime |  |
| TimeLastModified | datetime |  |
| TimeRaised | datetime |  |
| TimeResolved | datetime |  |
| Type | string | The name of the table |
