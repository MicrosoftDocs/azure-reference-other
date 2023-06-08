---
title: Azure Monitor Logs reference - HealthStateChangeEvent
description: Reference for HealthStateChangeEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# HealthStateChangeEvent

 Workload Monitor Health. This data represents state transitions of a health monitor.

## Solutions

- Azure Monitor for VMs
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| CurrentMonitorState | string | Current state of the monitor (Critical, Warning, Healthy, Unknown, None). |
| CurrentStateFirstObservedTimestamp | datetime | Timestamp (UTC) when the current state of the monitor was first observed. |
| EvaluationTimestamp | datetime | Timestamp (UTC) when the monitor health state change event was created. |
| Evidence | dynamic | Snapshot of samples and reason the monitor changed state. |
| ImpactStartTimestamp | datetime | Timestamp (UTC) the monitor start change to non-healthy (Critical, Warning) state. |
| InstrumentationData | dynamic | Current state of the monitor (Critical, Warning, Healthy, Unknown, None). |
| _IsBillable | string |  |
| MonitorConfiguration | dynamic | Configuration for the monitor. Aggregate monitor configuration is an empty string. |
| MonitoredObject | string | Object the monitor is monitoring. Values only exist for dynamic monitors, e.g. D: for monitor logical-disks\|D:\|free-space-mb. |
| MonitorName | string | Name of the monitor, e.g. logical-disks\|C:\|free-space-mb for Windows platform, filesystems\|/var/lib\|free-space-mb for Linux platform. |
| MonitorResourceId | string | ARM resource id of the monitor. |
| MonitorType | string | Type of the monitor. Same as the monitor name for static monitors, replaces MonitoredObject with * for dynamic monitors. |
| ParentMonitorName | string | Parent monitor name, e.g. logical-disks\|C: for Windows platform, filesystems for Linux platform. |
| PreviousMonitorState | string | Previous state of the monitor (Critical, Warning, Healthy, Unknown, None). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the record was generated. |
| Type | string | The name of the table |
