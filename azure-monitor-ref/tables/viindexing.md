---
title: Azure Monitor Logs reference - VIIndexing
description: Reference for VIIndexing table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# VIIndexing

 Indexing logs from Video Indexer.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Video Indexer




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountId | string | Video Indexer account ID. |
| AccountName | string | Video Indexer account name. |
| CorrelationId | string | A unique record identifier. |
| DurationMs | int | The operation duration in milliseconds. |
| ErrorCode | string | The error code if the operation failed |
| ErrorDescription | string | The description of the error code . |
| ExternalUserId | string | Caller external user Id. |
| IndexingProperties | dynamic | Properties of the indexing operation request. |
| Location | string | Video Indexer resource location. |
| OperationName | string | The name of the operation that triggered the event. |
| OperationVersion | string | Video Indexer operations API version. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| Status | string | Status of the operation, for example: Success, Failure, Warning, Informational or PartialSuccess. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| Type | string | The name of the table |
| Upn | string | Caller email. |
| VideoId | string | Video Indexer video ID. |
| VideoIndexerResourceId | string | Video Indexer resource ID. |
