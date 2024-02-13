---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/13/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Alert
---


| Column | Type | Description |
|---|---|---|
| AlertContext | string | Details of the data item that caused the alert to be generated in XML format. |
| AlertDescription | string | Detailed description of the alert. |
| AlertError | string |   |
| AlertId | string | GUID of the alert. |
| AlertName | string |   |
| AlertPriority | string |   |
| AlertRuleId | string |   |
| AlertRuleInstanceId | string |   |
| AlertSeverity | string | Severity level of the alert. |
| AlertState | string |   |
| AlertStatus | int |   |
| AlertTypeDescription | string |   |
| AlertTypeNumber | int |   |
| AlertValue | int |   |
| _BilledSize | real | The record size in bytes |
| Comments | string |   |
| Computer | string |   |
| Custom1 | string |   |
| Custom10 | string |   |
| Custom2 | string |   |
| Custom3 | string |   |
| Custom4 | string |   |
| Custom5 | string |   |
| Custom6 | string |   |
| Custom7 | string |   |
| Custom8 | string |   |
| Custom9 | string |   |
| Expression | string |   |
| Flags | int |   |
| FlagsDescription | string |   |
| HostName | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastModifiedBy | string | Name of the user who last modified the alert. |
| LinkToSearchResults | string |   |
| ManagementGroupName | string | Name of the management group for System Center Operations Manager agents.  |
| ObjectDisplayName | string |   |
| PriorityNumber | int |   |
| Query | string |   |
| QueryExecutionEndTime | datetime |   |
| QueryExecutionStartTime | datetime |   |
| RemediationJobId | string |   |
| RemediationRunbookName | string |   |
| RepeatCount | int | Number of times the same alert was generated for the same monitored object since being resolved. |
| ResolvedBy | string | Name of the user who resolved the alert. Empty if the alert has not yet been resolved. |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceType | string |   |
| ResourceValue | string |   |
| RootObjectName | string |   |
| ServiceDeskConnectionName | string |   |
| ServiceDeskId | string |   |
| ServiceDeskWorkItemLink | string |   |
| ServiceDeskWorkItemType | string |   |
| SourceDisplayName | string | Display name of the monitoring object that generated the alert. |
| SourceFullName | string | Full name of the monitoring object that generated the alert. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StateType | string |   |
| StatusDescription | string |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TemplateId | string |   |
| ThresholdOperator | string |   |
| ThresholdValue | int |   |
| TicketId | string | Ticket ID for the alert if the System Center Operations Manager environment is integrated with a process for assigning tickets for alerts. Empty of no ticket ID is assigned. |
| TimeGenerated | datetime |   |
| TimeLastModified | datetime |   |
| TimeRaised | datetime | Date and time that the alert was generated. |
| TimeResolved | datetime | Date and time that the alert was resolved. Empty if the alert has not yet been resolved. |
| TriggerId | string |   |
| Type | string | The name of the table |
| Url | string |   |
| ValueDescription | string |   |
| ValueFlags | int |   |
| ValueFlagsDescription | string |   |
