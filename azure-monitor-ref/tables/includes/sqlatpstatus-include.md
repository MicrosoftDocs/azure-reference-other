---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: SqlAtpStatus
---


| Column | Type | Description |
|---|---|---|
| AgentId | string | ID of the source monitoring agent |
| AgentStartTime | datetime | The start time of the Microsoft Monitoring Agent process running SQL ATP solution. This can help find agents who restart frequently or not at all and can indicate a problem or machine with out-of-date configuration |
| _BilledSize | real | The record size in bytes |
| ClientIP | string | Client IP address of the source computer |
| Computer | string | Name of the computer that hosts the SQL Server |
| HostResourceId | string | Resource ID of the machine hosting the SQL Instance, if exists |
| IntelligencePackVersion | string | The IP version of SQL Advanced Threat Protection running on the machine |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastError | string | The last error from SQL Advanced Threat Protection (if exists). The error refer to the time passed from the previous status entry and can help diagnose transient or persistent issues with SQL ATP protection |
| MachineUUID | string | The unique identifier of the machine running the Microsoft Monitoring Agent |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SqlInstanceName | string | SQL Server instance name |
| SqlInstanceStartTime | datetime | The start time of the SQL Server instance |
| SqlInstanceVersion | string | SQL Server instance version |
| Status | string | SQL Advanced Threat Protection status for the SQL instance |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated |
| Type | string | The name of the table |
