---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HuntingBookmark
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| BookmarkId | string | Guid - the bookmark ARM resource name |
| BookmarkName | string | Bookmark name given by the user |
| BookmarkType | string | Can be used to mark bookmark origin - currently not used |
| CreatedBy | string | JSON object with the user who created the bookmark, including: ObjectID, email and name |
| CreatedTime | datetime | The timestamp of bookmark first creation time |
| Entities | string | A serialized JSON of entities mapped by this bookmark |
| EventTime | datetime | The timestamp of the original event that is bookmarked |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastUpdatedTime | datetime | The timestamp of bookmark last update time |
| Notes | string | Notes provided by user |
| QueryEndTime | datetime | Query time range end time |
| QueryResultRow | string | JSON object with a single result row of the query |
| QueryStartTime | datetime | Query time range start time |
| QueryText | string | Original log analytics query text |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SoftDeleted | bool | Was the bookmark deleted by user |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string | Comma seperated list of tags provided by user |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the log |
| Type | string |   |
| UpdatedBy | string | JSON object with the user who last updated the bookmark, including: ObjectID, email and name |
