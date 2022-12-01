---
title: Azure Monitor Logs reference - VIAudit
description: Reference for VIAudit table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# VIAudit

 Audit logs from Video Indexer.

## Categories

- Audit
## Solutions

- LogManagement
## Resource types

- Video Indexer




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountId | string | The Video Indexer account ID. |
| AccountName | string | The Video Indexer account name. |
| CallerIpAddress | string | The caller IP address. |
| Claims | dynamic | Caller claims details. |
| CorrelationId | string | A unique record identifier. |
| Description | string | The operation description. |
| DurationMs | int | The operation duration in milliseconds. |
| ExternalUserId | string | Caller external user Id. |
| Location | string | The Video Indexer resource location. |
| OperationName | string | The name of the operation that triggered the event. |
| OperationVersion | string | The Video Indexer operations API version. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Signature | int | Http response signature of the operation, for example: 200, 401. |
| SourceSystem | string |  |
| Status | string | Status of the operation, for example: Success, Failure, Warning, Informational, Partial Success. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| Type | string | The name of the table |
| Upn | string | Caller email. |
| VideoId | string | The Video Indexer video ID. |
| VideoIndexerResourceId | string | The Video Indexer resource ID. |
