---
title: Azure Monitor Logs reference - Syslog
description: Reference for Syslog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# Syslog

 Syslog events on Linux computers using the Log Analytics agent.

## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string|Type of agent the data was collected from. For syslog the value is typically Linux.|
|TimeGenerated|datetime|Date and time the record was created.|
|Computer|string|Computer that the event was collected from.|
|EventTime|datetime|Date and time that the event was generated.|
|Facility|string|The part of the system that generated the message.|
|HostName|string|Name of the system sending the message.|
|SeverityLevel|string|Severity level of the event.|
|SyslogMessage|string|Text of the message.|
|ProcessID|int|ID of the process that generated the message.|
|HostIP|string|IP address of the system sending the message.|
|ProcessName|string|Name of the process that generated the message.|
|Type|string||
|_ResourceId|string||
