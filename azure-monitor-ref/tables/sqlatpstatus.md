---
title: Azure Monitor Logs reference - SqlAtpStatus
description: Reference for SqlAtpStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# SqlAtpStatus

 SQL Advanced Threat Protection status log. The logs allows identifying machines connected to the workspace with SQL ATP and the protection status on each instance on those machines.

## Solutions

- SQL Advanced Threat Protection




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AgentId | string | ID of the source monitoring agent |
| AgentStartTime | datetime | The start time of the Microsoft Monitoring Agent process running SQL ATP solution. This can help find agents who restart frequently or not at all and can indicate a problem or machine with out-of-date configuration |
| ClientIP | string | Client IP address of the source computer |
| Computer | string | Name of the computer that hosts the SQL Server |
| HostResourceId | string | Resource ID of the machine hosting the SQL Instance, if exists |
| IntelligencePackVersion | string | The IP version of SQL Advanced Threat Protection running on the machine |
| LastError | string | The last error from SQL Advanced Threat Protection (if exists). The error refer to the time passed from the previous status entry and can help diagnose transient or persistent issues with SQL ATP protection |
| MachineUUID | string | The unique identifier of the machine running the Microsoft Monitoring Agent |
| SourceSystem | string |  |
| SqlInstanceName | string | SQL Server instance name |
| SqlInstanceStartTime | datetime | The start time of the SQL Server instance |
| SqlInstanceVersion | string | SQL Server instance version |
| Status | string | SQL Advanced Threat Protection status for the SQL instance |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated |
| Type | string | The name of the table |
