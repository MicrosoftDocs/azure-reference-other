---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HealthStateChangeEvent
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CurrentMonitorState | string | Current state of the monitor (Critical, Warning, Healthy, Unknown, None). |
| CurrentStateFirstObservedTimestamp | datetime | Timestamp (UTC) when the current state of the monitor was first observed. |
| EvaluationTimestamp | datetime | Timestamp (UTC) when the monitor health state change event was created. |
| Evidence | dynamic | Snapshot of samples and reason the monitor changed state. |
| ImpactStartTimestamp | datetime | Timestamp (UTC) the monitor start change to non-healthy (Critical, Warning) state. |
| InstrumentationData | dynamic | Current state of the monitor (Critical, Warning, Healthy, Unknown, None). |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MonitorConfiguration | dynamic | Configuration for the monitor. Aggregate monitor configuration is an empty string. |
| MonitoredObject | string | Object the monitor is monitoring. Values only exist for dynamic monitors, e.g. D: for monitor logical-disks&#124;D:&#124;free-space-mb. |
| MonitorName | string | Name of the monitor, e.g. logical-disks&#124;C:&#124;free-space-mb for Windows platform, filesystems&#124;/var/lib&#124;free-space-mb for Linux platform. |
| MonitorResourceId | string | ARM resource id of the monitor. |
| MonitorType | string | Type of the monitor. Same as the monitor name for static monitors, replaces MonitoredObject with * for dynamic monitors. |
| ParentMonitorName | string | Parent monitor name, e.g. logical-disks&#124;C: for Windows platform, filesystems for Linux platform. |
| PreviousMonitorState | string | Previous state of the monitor (Critical, Warning, Healthy, Unknown, None). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the record was generated. |
| Type | string | The name of the table |
