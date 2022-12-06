---
title: Azure Monitor Logs reference - WVDManagement
description: Reference for WVDManagement table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# WVDManagement

 Windows Virtual Desktop Management Activity

## Categories

- Azure Virtual Desktop
## Solutions

- LogManagement
## Resource types

- Desktop Virtualization Host Pools
- Desktop Virtualization Application Groups
- Desktop Virtualization workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ArmObjectScope | string | The ARM object scope for the management request - used for session hosts, applications. |
| ClientSideIPAddress | string | The remote IP address from the client side. |
| CorrelationId | string | The activity Id. |
| ObjectsCreated | int | The number of objects that were created. |
| ObjectsDeleted | int | The number of objects that were deleted. |
| ObjectsFetched | int | The number of objects that were fetched. |
| ObjectsUpdated | int | The number of objects that were updated. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Route | string | The route for the management request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
| UserName | string | The user that initiated the management request. |
