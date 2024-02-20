---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: BehaviorAnalytics
---


| Column | Type | Description |
|---|---|---|
| ActionType | string | The specific type of action that triggered the event. |
| ActivityInsights | dynamic | Activity and behavioral insights. |
| ActivityType | string | The activity type that triggered the event. |
| ActorName | string | The name of the user initiating the action that generated the event. |
| ActorPrincipalName | string | The principal name of the user initiating the action that generated the event. |
| _BilledSize | real | The record size in bytes |
| DestinationDevice | string | The hostname of the destination device. |
| DestinationIPAddress | string | The destination IP address. |
| DestinationIPLocation | string | The destination Geo location based on the IP address. |
| Device | string | The name of the device on which the event occurred or which reported the event, depending on the schema. |
| DevicesInsights | dynamic | Devices metadata and insights. |
| EventProductVersion | string | The version of the product generating the event. |
| EventSource | string | Data source for this event. |
| EventVendor | string | The vendor of the product generating the event. |
| InvestigationPriority | int | Investigation priority score. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NativeTableName | string | The original table from which the record was fetched. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceDevice | string | The hostname of the source device. |
| SourceIPAddress | string | The source IP address. |
| SourceIPLocation | string | The source Geo location based on the IP address. |
| SourceRecordId | string | The unique Id of the source raw event. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetName | string | The name of the target user in the action that generated the event. |
| TargetPrincipalName | string | The name of the target user in the action that generated the event. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time when the raw event was generated (UTC). |
| TimeProcessed | datetime | Time when enrichment processing occurred (UTC). |
| Type | string | The name of the table |
| UserName | string | User name of the account. |
| UserPrincipalName | string | User principal name of the account. |
| UsersInsights | dynamic | Users metadata and insights. |
