---
title: Azure Monitor Logs reference - OEPDataplaneLogs
description: Reference for OEPDataplaneLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/1/2023
---

# OEPDataplaneLogs

 Contains logs for HTTP requests & responses for the Indexer Service API, in OSDU Data Platform, and Microsoft Energy Data Services. The Indexer service, indexes the metadata store to support search. The indexer service will automatically take items that are newly added to storage and index the attributes from the schema associated with the kind attribute.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft.OpenEnergyPlatform/energyServices




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Category | string | Logs generated as a result of operations executed using OAK APIs are grouped into categories. Categories in OAK are logical groupings based on the data source. |
| CorrelationId | string | Unique identifier to be used to correlate logs, when available. |
| _IsBillable | string |  |
| Location | string | The region of the resource emitting the event. |
| LogLevel | string | Log level of message (INFO, WARN, ERROR, etc.). |
| Message | string | Log details as a result of operation performed. |
| OperationName | string | The operation name for which the log entry was created. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
