---
title: Azure Monitor Logs reference - HealthStateChangeEvent
description: Reference for HealthStateChangeEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# HealthStateChangeEvent

 Workload Monitor Health. This data represents state transitions of a health monitor.

## Solutions

- Azure Monitor for VMs




## Columns

|Column|Type|Description|
|---|---|---|
|CorrelationId|string|Unique GUID of the monitor health state change event.|
|CurrentMonitorState|string|Current state of the monitor (Critical, Warning, Healthy, Unknown, None).|
|CurrentStateFirstObservedTimestamp|datetime|Timestamp (UTC) when the current state of the monitor was first observed.|
|Evidence|dynamic|Snapshot of samples and reason the monitor changed state.|
|impactStartTimestamp|datetime|Timestamp (UTC) the monitor start change to non-healthy (Critical, Warning) state.|
|InstrumentationData|dynamic|CorrelationIds and timestamps at various stages in the pipeline.|
|MonitorConfiguration|dynamic|Configuration for the monitor. Aggregate monitor configuration is an empty string.|
|MonitoredObject|string|Object the monitor is monitoring. Values only exist for dynamic monitors, e.g. D: for monitor logical-disks|D:|free-space-mb.|
|MonitorName|string|Name of the monitor, e.g. logical-disks|C:|free-space-mb for Windows platform, filesystems|/var/lib|free-space-mb for Linux platform.|
|MonitorResourceId|string|Monitor resource id of the monitor, e.g. ARM Id.|
|MonitorType|string|Type of the monitor. Same as the monitor name for static monitors, replaces MonitoredObject with * for dynamic monitors.|
|ParentMonitorName|string|Parent monitor name, e.g. logical-disks|C: for Windows platform, filesystems for Linux platform.|
|PreviousMonitorState|string|State of the monitor before this state change (Critical, Warning, Healthy, Unknown, None).|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|Timestamp (UTC) when the monitor health state change event was created.|
|Type|string|The name of the table|
