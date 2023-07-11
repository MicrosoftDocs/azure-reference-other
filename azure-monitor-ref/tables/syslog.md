---
title: Azure Monitor Logs reference - Syslog
description: Reference for Syslog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/10/2023
---

# Syslog

 Syslog events on Linux computers using the Log Analytics agent.

## Categories

- Virtual Machines
- Security
## Solutions

- LogManagement
## Resource types

- Kubernetes Services
- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets
- Azure Arc Enabled Kubernetes
- Azure Arc Provisioned Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real | The record size in bytes |
| CollectorHostName | string | Name of the remote device that generated the message. |
| Computer | string | Computer that the event was collected from. |
| EventTime | datetime | Date and time that the event was generated. |
| Facility | string | The part of the system that generated the message. |
| HostIP | string | IP address of the system sending the message. |
| HostName | string | Name of the system sending the message. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| ProcessID | int | ID of the process that generated the message. |
| ProcessName | string | Name of the process that generated the message. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SeverityLevel | string | Severity level of the event. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SyslogMessage | string | Text of the message. |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
