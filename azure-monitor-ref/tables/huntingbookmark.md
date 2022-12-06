---
title: Azure Monitor Logs reference - HuntingBookmark
description: Reference for HuntingBookmark table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# HuntingBookmark

 Azure sentinel hunting bookmarks audit table

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| BookmarkId | string | Guid - the bookmark ARM resource name |
| BookmarkName | string | Bookmark name given by the user |
| BookmarkType | string | Can be used to mark bookmark origin - currently not used |
| CreatedBy | string | JSON object with the user who created the bookmark, including: ObjectID, email and name |
| CreatedTime | datetime | The timestamp of bookmark first creation time |
| Entities | string | A serialized JSON of entities mapped by this bookmark |
| EventTime | datetime | The timestamp of the original event that is bookmarked |
| LastUpdatedTime | datetime | The timestamp of bookmark last update time |
| Notes | string | Notes provided by user |
| QueryEndTime | datetime | Query time range end time |
| QueryResultRow | string | JSON object with a single result row of the query |
| QueryStartTime | datetime | Query time range start time |
| QueryText | string | Original log analytics query text |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SoftDeleted | bool | Was the bookmark deleted by user |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string | Comma seperated list of tags provided by user |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the log |
| Type | string |  |
| UpdatedBy | string | JSON object with the user who last updated the bookmark, including: ObjectID, email and name |
