---
title: Azure Monitor Logs reference - CDBPartitionKeyStatistics
description: Reference for CDBPartitionKeyStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# CDBPartitionKeyStatistics

 This table provides outlier logical partition keys that have consumed more storage space than others, which can be valuable in debugging storage skews.

## Solutions

- LogManagement
## Resource types

- Azure Cosmos DB




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountName | string | The name of the Cosmos DB account containing the dataset for which partition key stats were generated. |
| CollectionName | string | The name of the Cosmos DB collection, which contains the partition. |
| DatabaseName | string | The name of the Cosmos DB database, which contains the partition. |
| PartitionKey | string | The logical partition key for which storage statistics were retrieved. |
| RegionName | string | The Azure region from which statistics for this partition were retrieved. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SizeKb | int | The storage size (in KB) for the logical partition key within the physical partition. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when statistics for this logical partition key were generated. |
| Type | string | The name of the table |
