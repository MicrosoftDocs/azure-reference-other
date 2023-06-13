---
title: Azure Monitor Logs reference - MCVPOperationLogs
description: Reference for MCVPOperationLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# MCVPOperationLogs

 The MCVP Azure monitor logs. This table will include logs for vehicle provision, connection and activities sending command and receiving telemetry messages.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft Connected Vehicle Platform




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| DeviceName | string | Device friendly name. |
| _IsBillable | string |  |
| Message | string | The general log message. |
| OperationName | string | The operation name where the log was created. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SeverityText | string | The log severity. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| SpanId | string | An identifier of the request as known by the caller. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) when the log was created. |
| TraceId | string | An identifier for distributed tracing through a system (W3C TraceContext). |
| Type | string | The name of the table |
| VehicleId | string | Unique vehicle identifier. |
