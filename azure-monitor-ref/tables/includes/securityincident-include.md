---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SecurityIncident
---


| Column | Type | Description |
|---|---|---|
| AdditionalData | dynamic | Additional data on the incident |
| AlertIds | dynamic | The IDs of the alerts related to the incident |
| _BilledSize | real | The record size in bytes |
| BookmarkIds | dynamic | The IDs of the bookmarks related to the incident |
| Classification | string | The classification the incident was given when closed |
| ClassificationComment | string | Description of the reason the incident was closed |
| ClassificationReason | string | The classification reason the incident was given when closed |
| ClosedTime | datetime | Timestamp (UTC) of when the incident was last closed |
| Comments | dynamic | The comments added to the incident |
| CreatedTime | datetime | Timestamp (UTC) of when the incident was created |
| Description | string | The description of the incident |
| FirstActivityTime | datetime | Timestamp (UTC) of when the first activity in the incident occured |
| FirstModifiedTime | datetime | Timestamp (UTC) of when the incident was first modified |
| IncidentName | string | The resource name of the incident |
| IncidentNumber | int | The sequential number of the incident |
| IncidentUrl | string | The URI to open the incident in Azure Sentinel portal |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Labels | dynamic | The labels added to the incident |
| LastActivityTime | datetime | Timestamp (UTC) of when the last activity in the incident occured |
| LastModifiedTime | datetime | Timestamp (UTC) of when the incident was last modified |
| ModifiedBy | string | The source of the change in the incident |
| Owner | dynamic | The user the incident is assigned to |
| ProviderIncidentId | string | The incident ID assigned by the incident provider |
| ProviderName | string | The name of the source provider that generated the incident |
| RelatedAnalyticRuleIds | dynamic | The IDs of the Analytic rules associated with the incident |
| Severity | string | The severity of the incident |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | The status of the incident |
| Tasks | dynamic | The tasks added to the incident |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) of when the incident was ingested |
| Title | string | The title of the incident |
| Type | string | The name of the table |
