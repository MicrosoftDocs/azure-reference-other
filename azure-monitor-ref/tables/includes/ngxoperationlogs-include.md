---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: NGXOperationLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Facility | string | The facility of log records from syslog as defined in RFC 3164.Facility can be one of kern, user, mail, daemon, auth, intern, lpr, news, uucp, clock, authpriv, ftp, ntp, audit, alert, cron, local0..local7. Default is local7. |
| FilePath | string | The file path where log records come from. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The location (region) the NGINX instance was accessed in. |
| Message | string | The message of the log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Severity | string | The severity of log records from syslog as defined in RFC 3164. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tag | string | The tag of log records from syslog. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log record was generated. |
| Type | string | The name of the table |
