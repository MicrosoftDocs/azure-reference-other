---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/08/2024
ms.author: orens
author: osalzberg
ms.custom: ContainerLog
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string | Computer/node that's generating the log. |
| ContainerID | string | Container ID for log source as seen by Docker engine. |
| Image | string | Container Image for log source as seen by Docker engine. |
| ImageTag | string | Used by Container solution only. Not populated by Azure Monitor for Containers. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogEntry | string | Actual log line. |
| LogEntrySource | string | Source of the log line. Possible values are stdout or stderr. |
| Name | string | Unique name of the container the form PODUid/ContainerName. |
| Repository | string | Used by Container solution only. Not populated by Azure Monitor for Containers. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| TimeOfCommand | datetime | Time that the agent processed the log. This is an optional field mainly useful for troubleshooting latency issues on the agent. |
| Type | string | The name of the table |
