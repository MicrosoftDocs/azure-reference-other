---
title: Azure Monitor Logs reference - AMSLiveEventOperations
description: Reference for AMSLiveEventOperations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AMSLiveEventOperations

 Contains logs related to a Live Event. Logs are sent when an encoder connects, disconnects, or if there is a discontinuity in the media data.

## Categories

- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Media Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| _IsBillable | string |  |
| Level | string | Message level. Possible values are Informational, Warning, Error, Critical and Verbose. |
| Location | string | Location of the service sending the event. |
| OperationName | string | The name of the operation that triggered the event. |
| Properties | dynamic | Operation details. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the event was generated. |
| Type | string | The name of the table |
