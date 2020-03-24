---
title: Azure Monitor Logs reference - SucceededIngestion
description: Reference for SucceededIngestion table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# SucceededIngestion

 Succeeded ingestion operations

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Data Explorer cluster




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|Time at which this event is generated and logged|
|OperationVersion|string|The version of this event|
|OperationName|string|The name of this operation|
|Category|string|The category of this log|
|CorrelationId|string|The ingestion source id|
|ResultType|string|The final state of this data ingestion operation|
|Database|string|The name of the database holding the target table|
|Table|string|The name of the target table into which the data is ingested|
|IngestionSourcePath|string|The Azure blob storage URI|
|SucceededOn|datetime|Time at which this ingest operation successfully ended|
|OperationId|string|The ingestion's operation Id|
|IngestionSourceId|string|A unique identifier representing the ingested source|
|RootActivityId|string|The ingestion's activity Id|
|Type|string||
|_ResourceId|string||
