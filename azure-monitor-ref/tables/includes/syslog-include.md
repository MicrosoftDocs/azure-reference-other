---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Syslog
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CollectorHostName | string | Name of the remote device that generated the message. |
| Computer | string | Computer that the event was collected from. |
| EventTime | datetime | Date and time that the event was generated. |
| Facility | string | The part of the system that generated the message. |
| HostIP | string | IP address of the system sending the message. |
| HostName | string | Name of the system sending the message. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ProcessID | int | ID of the process that generated the message. |
| ProcessName | string | Name of the process that generated the message. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SeverityLevel | string | Severity level of the event. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SyslogMessage | string | Text of the message. |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
