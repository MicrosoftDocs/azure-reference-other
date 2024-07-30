---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: Event
---


| Column | Type | Description |
|---|---|---|
| AzureDeploymentID | string | Azure deployment ID of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and collected from Azure storage. |
| _BilledSize | real | The record size in bytes |
| Computer | string | Name of the computer that the event was collected from. |
| EventCategory | int | Category of the event. |
| EventData | string | All event data in raw format. |
| EventID | int | Number of the event. |
| EventLevel | int | Severity of the event in numeric form. |
| EventLevelName | string | Severity of the event in text form. |
| EventLog | string | Name of the event log that the event was collected from. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ManagementGroupName | string | Name of the management group for System Center Operations Manager agents. For other agents this value is AOI-\<workspace ID\> |
| Message | string | Event message for the different Languages. The language is defined by the LCID attribute. |
| ParameterXml | string | Event parameter values in XML format. |
| RenderedDescription | string | Event description with parameter values. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | Role of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and collected from Azure storage. |
| Source | string | Source of the event. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
| UserName | string | User name of the account that logged the event. |
