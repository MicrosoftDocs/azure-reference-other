---
title: Azure Monitor Logs reference - HuntingBookmark
description: Reference for HuntingBookmark table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# HuntingBookmark

 Azure sentinel hunting bookmarks audit table

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log|
|BookmarkId|string|Guid - the bookmark ARM resource name|
|BookmarkName|string|Bookmark name given by the user|
|BookmarkType|string|Can be used to mark bookmark origin - currently not used|
|CreatedBy|string|JSON object with the user who created the bookmark, including: ObjectID, email and name|
|UpdatedBy|string|JSON object with the user who last updated the bookmark, including: ObjectID, email and name|
|CreatedTime|datetime|The timestamp of bookmark first creation time|
|LastUpdatedTime|datetime|The timestamp of bookmark last update time|
|EventTime|datetime|The timestamp of the original event that is bookmarked|
|QueryText|string|Original log analytics query text|
|QueryResultRow|string|JSON object with a single result row of the query|
|QueryStartTime|datetime|Query time range start time|
|QueryEndTime|datetime|Query time range end time|
|Notes|string|Notes provided by user|
|SoftDeleted|bool|Was the bookmark deleted by user|
|Tags|string|Comma seperated list of tags provided by user|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
