---
title: Azure Monitor Logs reference - MicrosoftDynamicsTelemetrySystemMetricsLogs
description: Reference for MicrosoftDynamicsTelemetrySystemMetricsLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# MicrosoftDynamicsTelemetrySystemMetricsLogs

 Microsoft Dynamics Telemetry System Metrics Logs

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log.|
|Category|string|Log category|
|EnvironmentId|string|Unique identifier for an environment as shown in Lifecycle Services|
|Role|string|Type of the machine (AOS/BI) emitting the events|
|RoleInstance|string|Name of the machine emitting the events|
|EventName|string|Name of the event|
|Type|string||
|_ResourceId|string||
