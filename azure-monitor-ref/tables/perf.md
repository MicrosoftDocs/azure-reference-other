---
title: Azure Monitor Logs reference - Perf
description: Reference for Perf table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# Perf

 Performance counters from Windows and Linux agents that provide insight into the performance of hardware components operating systems and applications.

## Columns

|Column|Type|Description|
|---|---|---|
|Computer|string|Computer that the event was collected from.|
|ObjectName|string|Name of the performance object.|
|CounterName|string|Name of the performance counter.|
|InstanceName|string|Name of the event instance. Empty if no instance.|
|CounterValue|real||
|TimeGenerated|datetime|Date and time the data was sampled.|
|SourceSystem|string|Type of agent the event was collected from. Possible values are OpsManager Linux and AzureStorage.|
|CounterPath|string|Full path of the counter in the form \\<Computer>\object(instance)\counter.|
|Min|real||
|Max|real||
|SampleCount|int||
|BucketStartTime|datetime||
|BucketEndTime|datetime||
|StandardDeviation|real||
|Type|string||
|_ResourceId|string||
