---
title: Azure Monitor Logs reference - Perf
description: Reference for Perf table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# Perf

 Performance counters from Windows and Linux agents that provide insight into the performance of hardware components operating systems and applications.

## Categories

- Virtual Machines
- Containers
## Solutions

- LogManagement
## Resource types

- Kubernetes Services
- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets
- Azure Stack HCI
- Azure Arc enabled Kubernetes




## Columns

| Column | Type | Description |
| --- | --- | --- |
| BucketEndTime | datetime |  |
| BucketStartTime | datetime |  |
| Computer | string | Computer that the event was collected from. |
| CounterName | string | Name of the performance counter. |
| CounterPath | string | Full path of the counter in the form \\&lt;Computer&gt;\object(instance)\counter. |
| CounterValue | real |  |
| InstanceName | string | Name of the event instance. Empty if no instance. |
| Max | real |  |
| Min | real |  |
| ObjectName | string | Name of the performance object. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SampleCount | int |  |
| SourceSystem | string | Type of agent the event was collected from. Possible values are OpsManager Linux and AzureStorage. |
| StandardDeviation | real |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the data was sampled. |
| Type | string | The name of the table |
