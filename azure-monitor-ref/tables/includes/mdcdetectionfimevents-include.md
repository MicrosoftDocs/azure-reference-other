---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/26/2024
ms.author: orens
author: osalzberg
ms.custom: MDCDetectionFimEvents
---


| Column | Type | Description |
|---|---|---|
| AgentId | string | Holds the Tivan Agent Id. |
| AzureResourceId | string | The Azure resource ID of the resource whose monitored entity was created, renamed, modified or deleted. |
| _BilledSize | real | The record size in bytes |
| Computer | string | The name of the machine on which the monitored entity was created, renamed, modified or deleted. |
| DataPipelineMetadata | dynamic | Holds Data PipelineMetadata. |
| EventType | string | The type of change that occurred on the entity. Must be either 'Created', 'Modified', 'Renamed' or 'Deleted'. |
| FileName | string | Holds the name of the file that was created, renamed, modified or deleted. |
| FilePath | string | Holds the path of the file that was created, renamed, modified or deleted. |
| FileType | string | Holds the type of the file that was created, renamed, modified or deleted. Example of possible values: Zip, PDF, Xar etc. |
| InitiatingProcessId | string | Holds the process Id of the initiating process that caused the monitored entity event. |
| InitiatingProcessName | string | Holds the name of the initiating process that caused the monitored entity event. |
| Inode | string | Holds the Tivan Agent Id. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsDir | bool | True if event is for a directory, false if event is for a file. |
| Region | string | The region the resource whose monitored entity was created, renamed, modified or deleted. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) when the monitored entity was created, renamed, modified or deleted. |
| Type | string | The name of the table |
