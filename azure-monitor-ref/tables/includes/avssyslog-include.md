---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AVSSyslog
---


| Column | Type | Description |
|---|---|---|
| AppName | string | The name of the application that generated this log, if available. |
| _BilledSize | real | The record size in bytes |
| Facility | string | Indicates the source that generated the syslog (e.g., an operating system, a process, an application, etc). |
| HostName | string | The name of the host that generated this log, if available. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogCreationTime | datetime | The time at which the log was created, if available. |
| Message | string | The entire syslog message. |
| MsgId | string | Identifies the type of message. For example, a firewall might use MSGID "TCPIN" for incoming traffic, and MSGID "TCPOUT" for outgoing traffic. Messages with the same MSGID reflect events of the same semantics. |
| ProcId | string | Identifies a process; specific usage varies from application to application. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Severity | string | The severity of the log. Acceptable values, in ascending level of severity: debug, info, notice, warn, err, crit, alert, emerg. This field may be empty. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time at which the log was ingested. |
| Type | string | The name of the table |
