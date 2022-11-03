---
title: Azure Monitor Logs reference - WVDSessionHostManagement
description: Reference for WVDSessionHostManagement table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# WVDSessionHostManagement

 Windows Virtual Desktop session host management data.

## Categories

- Azure Virtual Desktop
## Solutions

- LogManagement
## Resource types

- Desktop Virtualization Host Pools




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClientType | string | Information about the client that initiated the update (portal, Powershell etc.). |
| CorrelationId | string | The correlation ID for the activity. |
| CustomScriptAdded | string | A URL for the customer provided custom script or 'False' if none was provided. |
| ImageSource | string | The source for the Azure virtual machine - either Marketplace or Custom. |
| MaxVMsUnavailableDuringUpdate | int | The maximum number of virtual machines that might become unavailable during the host pool update operation. |
| NewVMSize | string | The desired Azure virtual machine size (e.g.: Standard_D2s_v4) after the host pool update. |
| NewVMSku | string | The desired Azure virtual machine SKU that will be used for the host pool update. |
| OSDiskSaved | bool | Property indicates whether the original disk is saved. |
| OSDiskType | string | The Azure storage disk type used for the host pool update. |
| ParentUpdateId | string | When the current host pool update is a retry or a resume of a previous host pool update operation, this represents the previous host pool update correlation ID. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ScheduledTime | string | When the host pool update is scheduled, the scheduled time. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
| UpdateMethod | string | The method that is used for the host pool update operation (e.g.: DiskSwap). |
| UpdateStatus | string | The current status of the host pool update operation. |
| UpdateType | string | The type of host pool update requested by the customer - whether Immediate or Scheduled. |
