---
title: Azure Monitor Logs reference - Watchlist
description: Reference for Watchlist table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/20/2021
---

# Watchlist

 An Azure Sentinel watchlist contains imported data that can be used to join or filter as an alert/incident condition.

## Categories

- Security
## Solutions

- Azure Sentinel




## Columns

|Column|Type|Description|
|---|---|---|
|AzureTenantId|string|The AAD TenantID to which this watchlist table belongs|
|CorrelationId|string|The ID for correlated events.|
|CreatedBy|dynamic|JSON object with the user who created the watchlist or watchlist item, including: ObjectID, email and name|
|CreatedTimeUTC|datetime|The time (UTC) when the watchlist or watchlist item was first created|
|DefaultDuration|string|JSON object describing he default duration to live that each item of a watchlist should inherit on creation|
|_DTItemId|string|The watchlist or watchlist-item unique Id. As an example, a watchlist 'RiskyUsers' can contain watchlist-item 'Name:John Doe; email:johndoe@contoso.com'. A watchlist-item has its unique Id and will belong to a watchlist. The containing watchlist can identified using the 'WatchlistId'|
|_DTItemStatus|string|Was the watchlist or watchlist item created, updated or deleted by user. As an example, a watchlist 'RiskyUsers' can contain watchlist-item 'Name:John Doe; email:johndoe@contoso.com'. If a watchlist is added, the the status would be 'Created'. If the name of the watchlist is updated from 'RiskyUsers' to 'RiskyEmployees' the status would be 'Updated' |
|_DTItemType|string|Distinguish between a watchlist and a watchlist-item. As an example, a watchlist 'RiskyUsers' can contain watchlist-item 'Name:John Doe; email:johndoe@contoso.com'. A watchlist-item type will belong to a watchlist type and the containing watchlist can identified using the 'WatchlistId'|
|_DTTimestamp|datetime|The time (UTC) when the event was generated|
|EntityMapping|dynamic|JSON object with Azure Sentinel entity mapping to input columns|
|LastUpdatedTimeUTC|datetime|The time (UTC) when watchlist or watchlist item was last updated|
|Notes|string|Notes provided by user|
|Provider|string|Input provider of the watchlist.|
|SearchKey|string|The SearchKey is used to optimize query performance when using watchlists for joins with other data.  For example, enable a column with IP addresses to be the designated SearchKey field, then use this field to join in other event tables by IP address.|
|Source|string|Input source of the watchlist.|
|SourceSystem|string||
|Tags|string|JSON array of tags provided by user|
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of when the event was generated.|
|TimeToLive|datetime|When a row is inserted into a watchlist, a TimeToLive value is added to that row based on the watchlist’s default duration value. When the row's specified TimeToLive timestamp passes, the system will ignore the row and consider the row deleted. A row's duration can be extended at any time by refreshing the row's TimeToLive.|
|Type|string|The name of the table|
|UpdatedBy|dynamic|JSON object with the user who last updated the watchlist or watchlist item, including: ObjectID, email and name|
|WatchlistAlias|string|Unique string referring to the watchlist|
|WatchlistId|string|The watchlist ARM resource name|
|WatchlistItem|dynamic|JSON object with key-value pairs from the input watchlist source|
|WatchlistItemId|string|The watchlist item unique Id|
|WatchlistName|string|Display name of Watchlist|
